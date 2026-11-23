# Adaptive Motion — implementation contract

## Animation maximalism
Keep abundant expressive, playful animations; animation for delight alone is valid. Do not flatten the product into generic minimal UI. Separate *semantic interaction* from *rendering richness*.

## Priority classes
- **A Touch:** input response, drag position, selection, drawing cursor; highest priority, never delay for decoration.
- **B Hero:** folding, throwing, unfolding, growing, burning, object movement; preserve timing, semantics and legibility.
- **C Detail:** particles, shadows, wobble, secondary motion; adjust density/resolution when stressed.
- **D Ambient:** stars, dust, clouds, background drift; first to pause/throttle under pressure or when offscreen.

## Adaptive controller rules
- Observe real frame timing/jank, lifecycle and user accessibility preferences; do not infer capacity only from model name.
- Begin with generous effects, then lower D and C quality after **sustained** evidence of overload; restore quality only after a longer stable period (hysteresis). Do not change levels every frame.
- Never change note burn/hold thresholds, drag hitboxes, storage semantics, accessibility state or haptic intent when adapting visual quality.
- Prefer object reuse, caching, dirty-region drawing (Canvas), avoiding unnecessary Compose recomposition/layout and offscreen suspension before reducing visible effects.
- Honor reduced-motion preferences with an accessible alternative; no uncontrollable flashing, forced waits or interaction-blocking flourishes.
- Use platform-specific adapters for Lab 1 Java/Canvas and Lab 2 Kotlin/Compose; share concepts and tests, **not** an untested cross-framework rendering implementation.

## Acceptance
Prototype and profile on representative devices before claiming the controller is implemented or performance is improved. Record before/after traces, actual frame pacing, heap and visual recordings. This file is a specification, not an implemented engine.
