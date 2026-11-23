# ZIMT design QA — evidence and acceptance checklist

A design release requires both functional tests and actual visual/interaction evidence. A green CI run **cannot** certify aesthetics, touch feel or real-device performance. Keep evidence links, device model/Android version, build SHA and reviewer observation; mark untested criteria as **UNVERIFIED**, not PASS.

## Design acceptance matrix
| Gate | What to inspect | Evidence |
|---|---|---|
| VIS-01 | Hierarchy, proportions, consistent typography, legibility, contrast and intentional negative space | Screenshots at compact and regular phone sizes |
| VIS-02 | Material fidelity, original asset integrity, shadows, depth, layering, transparent edges and clipping | Crops of key objects at multiple states |
| VIS-03 | Idle, pressed, selected, dragging, disabled, loading, error, empty, success and undo states as applicable | State screenshots / test script |
| MOT-01 | **Rich maximalist choreography:** varied microinteractions, joyful flourishes, anticipation/follow-through, secondary movement | Screen recording with interaction timeline |
| MOT-02 | Motion supports delight **without** blocking touch, reading or drawing; rapid repeats and cancellation recover cleanly | Real-device repeated-gesture recording |
| MOT-03 | Reduced-motion option, background/offscreen pause, low-end performance and no uncontrolled flashing/loops | Accessibility settings + older-device check |
| HAP-01 | Animation, haptics and optional audio align; graceful fallback if effect unsupported | Real-device hardware notes |
| UX-01 | Discoverability, touch target reachability, scroll/drag conflict, Undo and error recovery | Scenario test with observations |
| PERF-01 | No sustained jank, runaway allocations, battery-heavy ambient animations or retained offscreen animations | Profiling/recording when available |
| REG-01 | No accidental changes to protected assets, legacy data or existing interactions | Before/after comparison + functional tests |

## Reviewer procedure
1. Name the intended feeling and primary interaction before reviewing; identify project-specific visual language and constraints.
2. Capture the actual running app in representative states, including a short interaction recording. Do not substitute mockups for evidence.
3. Compare side by side with the prior approved state and original assets. Inspect compact screen, larger phone, dark/light/system text scale where relevant.
4. Test playful animation **and** cancellation, rapid input, background/resume, reduced motion and low-end performance. Keep expressive motion when it passes these constraints; do not arbitrarily remove it in the name of minimalism.
5. Record each gate as PASS / FAIL / UNVERIFIED with artifact, commit, device, date and exact observation. Critical failures block design approval; unavailable device tests remain unverified and must be disclosed.
6. Fix issues, recapture and re-review. Never claim “10/10”, pixel-perfect or production-ready without supporting evidence.

## Scope
This checklist does not authorize new features, replacement of user-provided art, or changes to app IDs. Future empty labs apply it only after the user defines the product.
