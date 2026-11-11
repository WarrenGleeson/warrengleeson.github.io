---
title: Revenue Investigation — Wave 40 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest Bubble native-mobile plugin concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 372
permalink: /projects/notes/revenue-investigation-wave-40-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-40, bubble, stage-4]
---

# Wave 40 Stage 4 — Implementation Plans

Planning only. No plugin development, Bubble Marketplace submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — EXIF / GPS metadata privacy sanitizer before upload

### MVP
- Bubble native-mobile plugin with one workflow action.
- Input: local image URI/file.
- Detect common EXIF fields and GPS metadata.
- Return structured metadata presence report.
- Optional strip-all or strip-GPS mode.
- Preserve visual orientation after rewrite.
- Return sanitized local URI/file plus before/after file sizes.
- Expose explicit failure state if sanitization cannot be verified.
- Support a deliberately small initial format set: JPEG first; add HEIC/PNG only after capability is verified.
- No cloud API or external account.

### Commercial model
- Prefer one-time US$10–35 license to reduce recurring support expectations.
- Bubble Marketplace handles purchase/remittance; Bubble currently retains 25% commission.
- Free demo/test plugin only if needed for discovery; avoid maintaining multiple codebases.

### Acquisition
1. Marketplace keywords: EXIF remover, GPS remover, image privacy, photo privacy, secure upload, metadata.
2. Listing screenshot should show `GPS detected -> removed -> safe file returned`.
3. Position as a companion to existing camera/upload plugins, not a replacement.
4. Privacy-first/on-device messaging is the primary differentiator.

### Main risks
- Codec/library behavior across iOS/Android.
- HEIC metadata rewriting may be materially harder than JPEG.
- Must fail visibly rather than claim sanitization when unsupported.

### Stage 4 verdict
**Best Wave 40 candidate for separate validation/build.**

---

## Rank 2 — Mobile media upload readiness preflight

### MVP
- One native workflow action accepting local image/file URI.
- Deterministic checks: MIME/type, extension, file size, width, height, aspect ratio, orientation.
- Optional image checks: brightness/sharpness threshold.
- Optional metadata flags: GPS/EXIF present.
- Builder-configurable min/max thresholds.
- Return `passes`, reason codes, human-readable reason and normalized metadata.
- No upload, compression or OCR in V1.

### Commercial model
- US$10–30 one-time license.
- Could bundle with the EXIF sanitizer later only if users clearly want one combined product; do not broaden architecture before validation.

### Acquisition
1. Keywords: mobile file validation, image validation, photo quality, upload preflight, Bubble mobile.
2. Position before existing uploader plugins: “reject bad files before you pay the upload/storage/support cost.”
3. Examples for inspection apps, marketplaces, profile photos and claim/evidence uploads.

### Main risks
- Quality heuristics can create support disputes.
- Keep the paid promise centered on deterministic validation; treat blur/brightness as configurable extras.

### Stage 4 verdict
**Strong simple plugin with broad compatibility and low infrastructure burden.**

---

## Rank 3 — Permission / device readiness checker for critical workflows

### MVP
- Configurable native readiness element/action.
- Initial supported checks: camera, photos/media, microphone, location and notifications only if stable APIs are available.
- Normalize platform-specific statuses into granted / denied / blocked / not-requested / unavailable.
- Expose aggregate `ready_to_start` state and per-capability reason codes.
- Optional connectivity/app-version checks if trivial.
- Optional open-settings action where supported.
- Never spam permission prompts automatically.

### Commercial model
- US$8–25 one-time, or US$1–3/month only if ongoing OS maintenance proves substantial enough to justify subscription pricing.

### Acquisition
1. Keywords: permission checker, camera permission, location permission, Bubble native mobile, app readiness.
2. Demo a multi-step field workflow that refuses to start until required capabilities are ready.
3. Position as workflow reliability rather than a generic device toolkit.

### Main risks
- iOS/Android permission semantics evolve.
- Bubble may add equivalent normalized permission handling natively.
- Higher ongoing maintenance than ranks 1–2.

### Stage 4 verdict
**Useful niche, but maintenance risk keeps it third.**

## Platform economics note

Bubble Marketplace supports one-time and recurring plugin pricing, but Bubble currently retains 25% of plugin license revenue. Native mobile plugin support became broadly available in 2026, creating fresh demand, but community evidence also shows plugin support can consume substantial time. The best strategy is therefore small plugins with few dependencies, no external service, explicit platform limits and a very narrow promise.

## Wave 40 conclusion

Top three:
1. EXIF / GPS metadata privacy sanitizer before upload
2. Mobile media upload readiness preflight
3. Permission / device readiness checker for critical workflows

Wave 40 differs from recent admin-preflight waves: the Bubble opportunity is **developer infrastructure sold as a tiny native capability**, with one-time pricing and minimal support rather than an ongoing SaaS service.

## Verification record
- Last verified: 2026-10-26
- Stage 4 status: complete
- Stage 5: explicitly out of scope
