---
title: Revenue Investigation — Wave 40 Stage 2 Viability Filter
summary: Viability filtering for Bubble native-mobile plugin ideas, prioritizing narrow privacy/upload/readiness utilities over crowded generic device features.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 370
permalink: /projects/notes/revenue-investigation-wave-40-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-40, bubble, viability]
---

# Wave 40 Stage 2 — Viability Filter

## Evidence that changed scoring

- Bubble supports paid plugins with monthly or one-time pricing, but retains 25% commission.
- Native mobile plugins became broadly publishable/monetizable in 2026, creating a newer surface than the mature web plugin ecosystem.
- QR/barcode, camera, OCR, contacts, speech/TTS, local storage, share sheet, calendar, biometrics and generic device-capability bundles already have current plugins.
- Offline Action Queue Mobile already exists, so generic offline queue/retry is dropped.
- Native file uploaders/downloaders and deep-link plugins already exist.
- Community evidence shows plugin support burden can materially exceed plugin revenue when products are broad or fragile, so narrow low-dependency utilities score higher.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | EXIF/GPS metadata privacy sanitizer before upload | 81 | Advance |
| 2 | Mobile media upload readiness preflight | 78 | Advance |
| 3 | Permission/device readiness checker for critical workflows | 75 | Advance |
| 4 | Secure clipboard auto-clear helper | 72 | Hold |
| 5 | Field evidence pack builder | 71 | Hold; overlaps camera/GPS primitives |
| 6 | App foreground/background lifecycle events | 69 | Hold; broader native utility overlap |
| 7 | Offline action queue | 50 | Drop; exact current competitor |
| 8 | Native file picker/uploader | 48 | Drop; direct competitors |
| 9 | Deep-link parser/router | 47 | Drop; direct/current overlap |
| 10 | QR/barcode scanner | 40 | Drop; crowded |
| 11 | OCR/document scanner | 40 | Drop; crowded |

## Stage 3 shortlist
1. EXIF/GPS metadata privacy sanitizer before upload
2. Mobile media upload readiness preflight
3. Permission/device readiness checker for critical workflows

## Verification record
- Last verified: 2026-10-26
- Stage 2 status: complete
- Stage 5: out of scope
