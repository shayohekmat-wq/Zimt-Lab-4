# ZIMT Development Doctrine 5.0 — binding cross-lab policy

**Outside maximalist; inside minimal.** Delightful materiality, animation and haptics are core product requirements. Reliable data, immediate input and measured compatibility are equally non-negotiable.

## Authority and scope
1. Latest explicit user instruction; data/privacy/signing safety always protected.
2. Lab-specific **ACTIVE_SCOPE.md** (current product truth) and actual source/verified tests.
3. This doctrine and lab-specific technical architecture.
4. Historical plans (reference only). Never treat an old checklist as a fresh feature request.

**No blanket feature freeze.** Independent new work can proceed while another feature is being verified. Do not release a specific high-risk change until its required evidence exists. Never let automation silently expand a frozen scope.

## Select workflow by actual risk, not by department
| Path | Applies to | Mandatory gate |
|---|---|---|
| Creative experiment | isolated visual assets, preview-only animation | visual review, provenance, no user-data impact; may stay on experiment branch |
| Product feature | interactive UI, navigation, motion, haptics | acceptance scenario, focused tests, build, cancellation/accessibility check |
| Safety critical | delete, move, Room, sync, permissions, user data | deterministic state transitions, idempotence, failure/lifecycle tests, migration/data regression |
| Release / migration | installable updates, package identity, signing | exact SHA CI, artifact provenance, certificate/version, install-over-existing-data check |

A change can require multiple gates. A successful compile is not visual approval; a device observation is not a data-migration test. Record PASS / FAIL / UNVERIFIED separately.

## Implementation rules
- **One authoritative interaction state** per gesture. Pointer adapter translates touch events; state machine decides transitions; UI observes state; repository executes confirmed data operations. No duplicate mutable boolean copies of the same phase.
- A destructive action must have a clear **commit point**, durable/reversible data semantics, and defined behavior when the animation is cancelled or the app backgrounds. Animations do not own persistence.
- Preserve stable IDs, original assets, release package/signing identity and existing data. Never add destructive Room fallback.
- Animation choreography: immediate feedback → primary action → material follow-through → optional delight. Each sequence supports interruption, background pause and reduced motion. Materials can have different physical responses.
- Moto G6 is a compatibility/performance reference, not a restriction on design ambition. Optimize measured input/GPU/memory bottlenecks. Equivalent experience may use different internal rendering implementations; no generalized adaptive engine by default.
- No speculative universal framework, event bus or cross-lab renderer. Share interfaces or code only when actual integration/use in multiple labs justifies it.
- Keep CI deterministic. Do not gate CI on unmeasured FPS or subjective aesthetics.

## Parallel development / automation
- Read actual HEAD, current scope, changed files and last evidence checkpoint at the start of every cycle.
- One owner per change. Work in separate branches for substantial parallel changes; avoid simultaneous edits to critical files.
- Integrate only after comparing HEAD, reconciling conflicts and running the relevant risk gates.
- Record commit SHA, implementation, tests actually run, unresolved risks and next action. A scheduled run or commit is not proof of success.
- Keep work small enough to review; no arbitrary mandatory timeboxes or forced extra management roles.

## Source of truth
**ACTIVE_SCOPE.md** = currently authorized product and constraints.
**ARCHITECTURE.md** (or equivalent) = technical decisions and data safety.
**DEVELOPMENT_STATUS.md** / **QUALITY_EVIDENCE.md** = factual implementation and verification.
Detailed specialist docs may remain, but must be linked and not conflict. Archive superseded plans instead of deleting history.

## Studio review gates
Design: screenshot + motion capture where available; Engineering: source and focused tests; Compatibility: real device traces for claims; Release: artifact/signature/update evidence. Review only the roles touched by the change's risk, not a ceremonial hierarchy.
