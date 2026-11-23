# Compatibility matrix — verification required

| Profile | Coverage | Status |
|---|---|---|
| Nothing Phone 3a | Main device: touch, 60/120 Hz behavior where supported, haptic fallbacks, motion and background/resume | UNVERIFIED |
| Motorola Moto G6 | Older/low-power hardware, touch and vibration support, memory, lifecycle and long animation runs | UNVERIFIED |
| Small phone / large text | Touch targets, clipping, orientation and scrolling | UNVERIFIED |
| Current Android emulator | Build smoke, lifecycle and instrumentation where available | UNVERIFIED |

## Repository-specific Android API floor
- **Lab 1:** Java/Android Canvas, `minSdk 23` (Android 6.0), `targetSdk 34` at audit. Verify API 23 plus actual installed Moto G6 OS. Lab versions use distinct application IDs: no automatic private-data migration.
- **Lab 2:** Kotlin/Compose, `minSdk 26` (Android 8.0), `targetSdk 36` at audit. Verify API 26 plus actual installed Moto G6 OS. Stable release package and original signing key are required for update-in-place; debug suffix installs separately.
- **Lab 3/4:** Not yet specified. Do not invent SDK floors, package IDs or a tech stack before a product brief.

## Required scenario coverage
Cold start; first interaction; 100 repeated touches/drag cycles; rapid cancel/multitouch; rotation; app background/foreground; process recreation; reduced-motion setting; disabled/unavailable haptic effects; 15-minute active animation; data persistence and update migration when applicable.

Mark every result PASS / FAIL / UNVERIFIED with real evidence. Declared API support is not proof of device compatibility.
