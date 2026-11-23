# Performance budget — proposed targets, not measured results

## Non-negotiable priority
ZIMT is **animation-maximalist**. Preserve rich, joyful animations and immediate touch feedback. Optimize wasted work first; dynamically reduce decorative rendering complexity before degrading primary interactions. Never trade data integrity or correct gesture semantics for speed.

## Initial measurable targets
- Input: visual touch response on the next renderable frame where feasible; record actual input-to-display latency on devices rather than asserting a universal threshold.
- 60 Hz: aim for >=95% frames within 16.7 ms in a repeatable interaction scenario; 120 Hz: record 8.3 ms frame budget when the device and rendering path support it.
- No sustained memory growth after 100 repeated interactions; compare stabilized heap after GC and inspect native/bitmap allocations.
- Decorative animation must pause when offscreen/backgrounded. Avoid per-frame object allocation and redundant full-screen redraw.
- Run >=15 minutes of representative motion on an actual device before declaring thermal/performance acceptance.
- Collect cold-start, time-to-interactive, jank/frame timelines, peak heap, battery/thermal observations and device/OS/build SHA. **All targets remain PROPOSED until baselines exist.**
- A missing benchmark or device does not count as PASS. Document UNVERIFIED and continue independent engineering tasks.

## Evidence and release gate
Keep per-scenario baseline, device, Android version, refresh rate, build SHA, capture date, raw trace/screenshot link and regression verdict. Reject known data loss, broken touch/cancel, crashes and severe sustained jank. Avoid rigid global timing thresholds on emulators or shared CI hosts.
