# Motion First 2.2 — lean execution contract

## Decision
**Moto-G6-first.** Preserve maximalist, joyful motion with the same choreography on supported devices. No generalized adaptive quality engine, no device performance polling, no arbitrary particle-count reductions. Optimize actual bottlenecks only.

## Three priorities (in order)
1. **Input:** drag, touch, drawing and cancellation are never blocked by decoration; preserve exact gesture semantics and persistence.
2. **GPU:** profile overdraw, translucent fullscreen layers, blur/shadow passes and unnecessary redraw/recomposition. Prefer measured cheap transforms, clipped drawing and appropriately sized cached assets. A full 2160x1080 RGBA8888 buffer is 9,331,200 bytes = 8.90 MiB; copies can exhaust memory.
3. **Memory/consistency:** decode assets off animation-critical paths, avoid per-frame allocations, release inactive resources and pause offscreen animation.

## Measurement protocol
- **Baseline before code change.** Record build SHA, phone model/OS/RAM, battery and thermal state, refresh rate, scene, iteration count and traces. Test release-like/profileable builds; debug timing is not a release performance claim.
- **Repeatable scenarios:** cold start; 100 consecutive drag/draw cycles; fold/throw or relevant primary animation; overlapping animations; background/resume; 15-minute stress; data retention after process restart.
- **Frame metrics:** track actual presentation/jank where supported; on Android 8/9 use available FrameMetrics/graphics traces and device tooling. Do **not** rely on Android 12+ `frameOverrunMs` on Moto G6. Separate CPU frame duration from GPU bottlenecks.
- **Prioritize worst frames:** inspect P95/P99 and missed frames, not just mean FPS. 16.67 ms is a 60 Hz frame period, not a guarantee of end-to-end latency.
- **A/B comparison:** same physical device, OS, scenario, compilation state and similar thermal conditions; >=3 repeat runs; preserve raw evidence. Mark unrun checks UNVERIFIED.

## Optimization decision rule
Only accept an optimization if it preserves the design/gesture behavior and improves the measured bottleneck without meaningful regressions in memory, thermal behavior or stability. Never add sprite sheets, caching, Baseline Profiles or benchmark dependencies solely because they sound faster; evaluate after profiling.

## Deferred ZIMT Performance Lab
A **separately installable**, offline-first APK with no production user data. A one-tap scenario suite should measure frame pacing/jank, CPU/UI timings where available, heap/bitmap memory, startup and lifecycle; export privacy-preserving JSON and readable summary with device/OS/build/scenario. The user runs it on a real Moto G6 and shares the report. Make the measurement module portable to main ZIMT. Android 8/9 metric limitations must be explicitly represented; no fabricated GPU utilization or thermal readings.

## Project boundaries
Lab 1: Java/Canvas, protect drawing and non-destructive editing. Lab 2: Kotlin/Compose, protect original PNG layers, Room data, note gesture thresholds, cancellation, signing and update identity. Labs 3/4: document standard only until scoped. Check `docs/MOTO_G6_REFERENCE.md` for historical hardware benchmarks, which are not UI FPS measurements.

## References
- https://developer.android.com/topic/performance/rendering/inspect-gpu-rendering
- https://developer.android.com/topic/performance/measuring-performance
- https://developer.android.com/topic/performance/benchmarking/macrobenchmark-metrics
