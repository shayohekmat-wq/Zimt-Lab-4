# ZIMT Lab — engineering agent contract

## Mission and authority
Build a polished, reliable, independently testable Android lab whose features can later be integrated into the main ZIMT app. The **latest explicit user request** controls product scope; preserve established safety, privacy and data-integrity requirements. Read the repository README, current source and any active product plan before implementing. Never assume requirements or a framework from another lab apply here.

## Execution protocol
1. Inspect actual HEAD, relevant code, existing tests, CI configuration and the most recent verified checkpoint. Identify a concrete, end-to-end acceptance target; avoid repeating planning when implementation is possible.
2. Implement a coherent vertical slice: UI, state, persistence, animations/haptics where applicable, accessibility, cancellation and error handling, and focused tests. Preserve modularity and integration boundaries. Keep app-specific shell and package identity separate from reusable feature logic.
3. Build/test after meaningful changes, **read the real output**, repair failures and rerun. A commit, tool success, green compilation or launched CI job is not proof of product completion. Avoid needless build loops and version bumps.
4. Validate the strongest available evidence: unit tests, integration tests, CI, Android device behavior and upgrade compatibility. Record what was actually verified; mark device-only observations as unverified if no device was available.
5. For requested APK updates, verify exact source commit, applicationId, monotonic versionCode, correct original signing certificate, installability and existing-data retention. Never distribute an unsigned/debug APK as a safe update or expose signing secrets.
6. Stop at a delivered, verified result or a genuine tool/execution blocker after completing other independent work. When interrupted, leave a concise factual checkpoint (commit, tests, unresolved acceptance criteria and next executable action); resume from it rather than starting another plan.

## Non-negotiable engineering safeguards
- **No silent data loss:** never reset databases or discard user drawings, notes or settings to simplify an update. Test migrations and backups when relevant.
- **Portability to ZIMT:** keep domain models and business logic reusable, isolate Android Activity/navigation and storage adapters, use stable IDs and explicit interfaces. Different app IDs do not share private Android data automatically; design a tested export/import or migration path.
- **Reliability and UX:** handle gesture cancellation, multitouch, rotation/backgrounding, reduced motion, older supported Android versions and low-end hardware as relevant. Do not assert device behavior based only on source inspection.
- **Security:** do not commit private keys, tokens or credentials; do not introduce network services or permissions without a product need.
- **Scope discipline:** no speculative redesign, new features or destructive refactors in place of the requested milestone.

## Design-director quality gate
- **Animation-maximalist by default:** build many delightful, varied, tactile microinteractions and expressive transitions; motion can exist simply for joy and personality. Do not interpret “intentional” as “minimal”. Layer primary action, secondary material response and optional playful flourish. Keep interactions responsive, cancellable, accessible and efficient on supported older devices.
- Treat art direction, visual hierarchy, material authenticity, coherent states, animation, haptics and optional sound as first-class acceptance criteria. Inspect actual screenshots and recordings where tools permit; a green build is not design approval.
- Read `docs/DESIGN_PRINCIPLES.md` and `docs/DESIGN_QA.md` before implementing or approving UI changes. Capture PASS/FAIL/UNVERIFIED evidence for relevant visual, motion and usability gates. Never claim device or visual QA when not performed.
- Preserve the project's own art direction, original user assets and feature scope. No generic template UI or arbitrary removal of playful animation merely for simplicity.

## Compatibility and performance release gates
- Read `docs/MOTION_FIRST_PLAN.md`, `docs/MOTO_G6_REFERENCE.md`, `docs/PERFORMANCE_BUDGET.md` and `docs/COMPATIBILITY_MATRIX.md` before changing rendering, gestures, animation or supported Android versions.
- Preserve **animation maximalism**. Prioritize immediate touch/drawing and primary interactions; profile the Moto G6 first and optimize measured GPU/CPU/memory bottlenecks without introducing generalized adaptive quality tiers. Pause offscreen animation, avoid per-frame allocations and lifecycle leaks.
- Measure on representative devices or explicitly report **UNVERIFIED**. Never claim 60/120 Hz smoothness, memory stability, battery efficiency or compatibility based only on compilation. Record device, OS, build SHA, scenario and evidence.
- Do not silently raise minSdk, change package identity, weaken data migration, or alter gesture timing to meet performance targets. Separate project-specific implementations from portable ZIMT interfaces.

## Communication and recovery
For direct implementation orders, avoid progress-only messages and premature completion reports. Distinguish **verified**, **implemented but untested**, **incomplete** and **blocked**. If no project-specific checkpoint exists, create one only when a real interruption makes it useful. These instructions cannot extend execution limits or schedule background work.

## Unassigned lab — activation gate
This repository is intentionally a **blank future lab**. Do not invent a product concept, Android package ID, tech stack, signing identity, SDK level, UI design or build pipeline.
Before first implementation, confirm the user's intended lab idea, create a short project-specific README/acceptance criteria, inspect any shared ZIMT interfaces, and choose the smallest maintainable implementation. Preserve the ability to install the lab separately and integrate its modules into ZIMT later.

### Motion First 2.2 — binding strategy
- **Moto-G6-first, not generalized adaptive quality control:** follow `docs/MOTION_FIRST_PLAN.md` and researched `docs/MOTO_G6_REFERENCE.md`. The older `docs/ADAPTIVE_MOTION.md` now explicitly defers to this decision.
- Optimize actual expensive animations while preserving maximalist motion, identical interaction choreography and input priority. No automatic quality tiers unless measured failures require a narrow exception.
- **Deferred ZIMT Performance Lab:** separately installable, privacy-preserving, user-run physical-device test APK; record real frame/jank/memory/lifecycle metrics and export reports. Do not claim a real Motorola test before it happens.
