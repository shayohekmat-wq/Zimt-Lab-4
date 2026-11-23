# Future ZIMT integration — minimal interfaces (proposal only)

Do **not** create a universal framework or force Canvas and Compose into one renderer. Each Lab stays independently installable and data-safe.

1. **Lifecycle boundary:** module entry/exit, background/foreground, restoration; host-owned navigation. Define a concrete `ZimtModule` interface only when integration is scheduled.
2. **Haptic intent:** semantic events (lift, drop, confirm, warning, cancel), with tested Android-version/device fallbacks. No assumptions that specific vibrator primitives work.
3. **Versioned data exchange:** stable IDs, explicit schema version, export/import validation, no destructive migration; host must not read internal Room files directly.
4. **Design tokens:** colors, typography, spacing and material vocabulary as documentation initially; no shared UI library until at least two Labs need it.

Compatibility: Lab 1 Java/Canvas API23; Lab 2 Kotlin/Compose API26; avoid raising either floor. Labs 3/4 intentionally have no product/SDK decisions.

Quality sequence: PLANNED → IMPLEMENTED → CI_VERIFIED → DEVICE_VERIFIED. See `docs/QUALITY_EVIDENCE.md`.
