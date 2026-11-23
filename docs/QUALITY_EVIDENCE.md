# Evidence ledger — ZIMT quality gate

Use the sequence **PLANNED → IMPLEMENTED → CI_VERIFIED → DEVICE_VERIFIED**. Never skip a state or infer device verification from a successful build. Record each feature separately.

| Feature / claim | Source implementation | CI evidence (run URL + SHA) | Device evidence (model, OS, video/trace) | Current status |
|---|---|---|---|---|
| Moto G6 60 Hz animation performance | Motion First specification only | None | None | PLANNED / UNVERIFIED |
| Visual design and haptic quality | Design principles and QA contract | Not a CI-verifiable aesthetic property | None | PLANNED / UNVERIFIED |
| Standalone Performance Lab APK | Backlog in Motion First plan | None | None | PLANNED |
| Future ZIMT module portability | Interface proposal | None | None | PLANNED |

## Release gate
1. Exact commit builds and tests pass; retain CI run URL and test reports.
2. Data integrity, lifecycle and gesture cancellation have specific tests; manual device checks for haptics/visuals.
3. Confirm actual applicationId, monotonically increasing versionCode, original release certificate and upgrade from existing user data.
4. A missing test is UNVERIFIED, not PASS. Never represent a proposed architecture as production code.
5. Protect user drawings, notes, asset originals, IDs, and existing installs.

## New ideas: admission rule
Capture user goal, visual interaction sketch, acceptance criteria, minimum supported API, expected Moto G6 load, persistence impact, haptic fallback and future ZIMT interface. Prototype the smallest slice. Only extract a shared library after two Labs demonstrate the same real requirement. Do not add features to blank Labs 3/4 without an explicit brief.
