# Performance budget — Moto-G6-first (unmeasured targets)

**Source of truth:** `docs/MOTION_FIRST_PLAN.md`; hardware: `docs/MOTO_G6_REFERENCE.md`.

## Acceptance dimensions
- Touch: visual response on next feasible frame; preserve cancellation, gestures and data.
- Frame pacing: record P50/P95/P99 and missed-frame percentage for fixed scenarios; provisional target >=95% frames meeting 16.67 ms 60 Hz frame period, subject to actual device baseline. Do not equate CPU frame duration with completed GPU presentation.
- Memory: no sustained heap/bitmap growth after 100 repeated interactions; measure stable state and peak usage.
- Lifecycle: no offscreen decorative rendering; correct resume, rotation and process recreation.
- Thermal: >=15-minute physical-device test; note temperature/thermal indicators if available, and battery state. Never fabricate measurements.
- Compare >=3 runs of release-like/profileable builds under comparable conditions, not debug-only timing. Record actual OS, model, refresh rate, build SHA and raw trace.

## Status
All physical Moto G6 app measurements: **UNVERIFIED** until device test. Published 3D benchmarks do not establish ZIMT animation FPS.

## Release gate
Reject known crashes, data loss, broken gestures or verified severe regressions. Do not block CI on uncalibrated emulator frame thresholds. Use PASS / FAIL / UNVERIFIED with evidence.
