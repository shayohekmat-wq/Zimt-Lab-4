# Motion First 2.1 — Moto-G6-first implementation plan

## Binding decision
**Replace the proposed complex Adaptive Motion Engine with Moto-G6-first optimization.** Maintain maximalist, delightful animation, one consistent choreography across supported devices, and immediate touch response. No continuous device-performance classifier, multiple dynamic render-quality tiers or automatic animation-count reductions unless real measurements justify a narrowly scoped exception.

## Implementation order
1. Establish reproducible benchmark scenarios and trace baseline before changing animation code.
2. On Moto G6 prioritize touch latency, frame pacing, heap and thermal stability; optimize the most expensive actual animations first.
3. Prefer cached/appropriately sized imagery, transforms, bounded overdraw, avoiding unnecessary redraws/recompositions and per-frame allocations; measure tradeoffs. Never assume sprite sheets are faster without memory checks.
4. Preserve all gesture thresholds, cancellation semantics, persistent data, existing original PNG layers, app identity and signing. Never silently raise minSdk.
5. Retest on Moto G6 and Nothing Phone 3a. Document PASS / FAIL / UNVERIFIED with build SHA, Android version and raw trace.
6. Only minimal fallback: pause offscreen/background animations, honor reduced motion, address verified device/driver bugs. No generalized adaptive engine.

## Deferred project: standalone ZIMT Performance Lab
Plan a **separately installable** Android APK, modular for future ZIMT integration; do not build it without prioritization. One-tap scripted 2–15 min tests, app-representative paper fold/throw, bucket wobble, dragging/drawing, layered alpha and particles. Measure frame timing/jank, heap and bitmap allocation, cold start, lifecycle and thermal/battery indicators when available. Record actual device model, RAM, OS, refresh rate, battery/thermal state, app SHA, scenario, timestamps and version. Export shareable JSON plus human-readable report; no personal notes/content; avoid sensitive identifiers; no network required. Physical phone run by user, analysis by assistant. Tests must never alter production data.

## Source hardware and historical benchmarks
See `docs/MOTO_G6_REFERENCE.md`. Historical 3D scores are *not* expected ZIMT UI fps. Current device measurements remain UNVERIFIED.

## Architecture
Lab 1 Java/Canvas and Lab 2 Kotlin/Compose use separate optimization implementations; Labs 3/4 inherit the quality contract but no invented app architecture. Integrate future modules into ZIMT through clear interfaces.
