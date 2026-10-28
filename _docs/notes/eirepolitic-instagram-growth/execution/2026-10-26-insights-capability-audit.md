---
title: "EirePolitic Instagram Growth: Insights Capability Audit — 2026-10-26"
description: "Live read-only capability audit of the production Instagram credential before implementing Insights ingestion."
group: "Notes"
order: 71
---

# Instagram Insights Capability Audit — 2026-10-26

## Purpose

Record the first live execution result from Queue 0 of the EirePolitic Instagram audience-growth programme.

This audit was read-only against production runtime state. It did not publish content, deploy infrastructure, rotate credentials, alter AWS resources, or modify the production Instagram publisher.

## Repository / runtime inspected

Production repository:

`warrengleeson/Eirepolitic-data-pipeline`

Relevant runtime facts verified from current `main`:

- Meta host: `graph.facebook.com`
- Graph API version used by publisher: `v25.0`
- authentication path: Instagram API with Facebook Login / Page access token
- production secret: `eirepolitic/instagram/publishing`
- secret contains the existing Page access token and Instagram professional-account ID
- production publication ledger remains `eirepolitic-publications`

## Audit execution

A temporary audit branch was created in the production repository:

`audit/instagram-insights-capability`

The branch adds a read-only GitHub Actions probe that:

1. obtains the existing Instagram publishing credential from AWS Secrets Manager inside the runner;
2. does not print or persist the credential;
3. queries basic Instagram account metadata;
4. enumerates recent media;
5. probes account-level Insights metrics;
6. probes media-level Insights metrics;
7. writes only a sanitised supported/unsupported capability matrix to the audit branch.

No production deploy steps execute on the audit branch.

## Live result

### Basic account access — PASS

The existing credential successfully returned basic Instagram professional-account fields including:

- `username`
- `media_count`
- `followers_count`

This confirms:

- the secret is valid for basic account access;
- the Instagram professional account is reachable;
- the current Facebook Login/Page-token path is functional.

### Media enumeration — PASS

The credential successfully returned 25 recent media records during the probe.

Observed current media types:

- `CAROUSEL_ALBUM`

Observed media product type:

- `FEED`

This confirms the future collector can enumerate existing media and map media IDs to EirePolitic publication records.

### Account Insights — BLOCKED BY PERMISSION

Every probed account-level Insights metric returned:

```text
OAuthException
code: 10
(#10) Application does not have permission for this action
```

Metrics probed included:

- `views`
- `reach`
- `accounts_engaged`
- `total_interactions`
- `likes`
- `comments`
- `saves`
- `shares`
- `reposts`
- `follows_and_unfollows`
- `profile_links_taps`

### Media Insights — BLOCKED BY PERMISSION

Every probed media-level Insights metric returned the same OAuth permission error.

Metrics probed included:

- `views`
- `reach`
- `likes`
- `comments`
- `saved`
- `shares`
- `reposts`
- `total_interactions`
- `follows`
- `profile_visits`
- `profile_activity`
- Reel watch-time metrics

The failure is therefore not a metric-name or media-type problem at this stage. The Insights edge itself is blocked by app/token permission.

## Diagnosis

The current production credential has enough permission for the existing basic/publishing path but does not currently have the permission required to read Instagram Insights.

For the current Facebook Login architecture, Meta's Insights documentation requires:

- `instagram_basic`
- `instagram_manage_insights`
- `pages_read_engagement`

Meta also documents `pages_show_list` as part of the Facebook Login permission dependencies/connection flow.

If the Page role was granted through Business Manager, Meta documentation may also require `ads_management` and `ads_read`; verify the live account/app relationship before requesting these because they should not be added unnecessarily.

## Architectural consequence

**Do not create the analytics DynamoDB table, collector Lambda, backfill process, or dashboard yet.**

The correct next step is to repair/extend the Meta app authorisation and then rerun this same read-only capability audit.

Once the Insights permission works, the audit must be rerun to discover the exact metric matrix supported by this account/API version. Only then should the storage schema be finalised.

## Required next action

The Meta app/token needs to be re-authorised with `instagram_manage_insights` for the existing Facebook Login path, while preserving the working publishing permissions and credential architecture.

Do not:

- migrate to Instagram Login merely for this task;
- rotate the publishing token unless the re-authorisation flow requires a replacement token;
- remove existing publishing permissions;
- change the Instagram professional account/Page linkage;
- create a second Meta app unless the existing app cannot support Insights permission;
- paste any token into chat or GitHub.

## Validation after re-authorisation

Rerun the audit branch and require:

1. account basic access still passes;
2. media enumeration still passes;
3. at least one account Insights metric succeeds;
4. at least one feed-media Insights metric succeeds;
5. the capability matrix records exact supported/unsupported metrics;
6. publishing health remains unchanged.

Only after those checks pass should Workstream 01 move to analytics-storage design and backfill implementation.

## Queue 0 status

| Item | Status |
|---|---|
| Insights repository/runtime audit | Complete |
| Basic account capability | Pass |
| Media enumeration | Pass |
| Account Insights capability | Blocked — Meta permission |
| Media Insights capability | Blocked — Meta permission |
| Analytics schema implementation | Not started — correctly blocked |
| Profile baseline audit | Pending |
| Experiment metadata convention | Pending |

## Source-of-truth audit artifact

The sanitised live capability matrix is stored only on the temporary audit branch in:

`audit-results/instagram-insights-capability.json`

The audit branch is not intended to be merged into production in its current branch-specific form.
