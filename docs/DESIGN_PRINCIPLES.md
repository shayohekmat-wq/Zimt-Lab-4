# ZIMT design principles — design-director contract

**Ambition:** An unmistakably crafted, delightful, tactile mobile experience. Design quality is a product requirement, not post-build decoration. This document complements `AGENTS.md`; the latest explicit user instructions and established product scope take precedence.

## 1. Maximalist motion, intentional delight
**Animation-maximalist by default:** Prefer many varied, charming, satisfying microinteractions and rich transitions, not a minimal-motion aesthetic. Motion may exist purely for joy, surprise, personality or playful reward; it does **not** have to convey functional information every time. Nevertheless every motion must fit the product's character, remain legible and controllable, and avoid obstructing core tasks.
- Animate touch-down, lift, hover/drag, release, success, undo, selection, navigation, object interactions, material responses and playful secondary details when appropriate. Compose sequences with anticipation, follow-through, squash/stretch, secondary motion and stagger; avoid identical stock easing everywhere.
- Use physical metaphors when helpful: paper folds and flutters; woven/wooden/metal containers react with distinct inertia; drawings and plants grow organically. Preserve individual app identities; never force bucket aesthetics into the garden.
- **Layered motion hierarchy:** immediate touch feedback; primary object action; secondary material/ambient response; optional flourish. Primary interaction must remain clear even during elaborate choreography.
- No gratuitous input latency, uncontrollable loops, flashing, forced waiting, overlapping effects that obscure controls, or excessive CPU/battery consumption. Ambient motion should be low-cost, pause when offscreen/backgrounded, and never steal attention from reading or drawing.
- Respect system reduced-motion and accessibility preferences with a calmer but still understandable mode; keep all functionality available. Handle cancellation, rapid repeated taps, rotation, process recreation and older supported devices.

## 2. Art direction and visual craft
- Define visual hierarchy, spacing, typography, palette, lighting, materials, silhouette, depth, contrast and interaction states before polishing isolated controls.
- Favor bespoke, cohesive, emotionally resonant details over generic template styling. Standard Android controls are welcome when they improve clarity; customize only with a reason.
- Make materials convincing and consistent: texture, wear, shadows, reflection, layering, edge treatment and response to touch should agree. Never deform or replace protected original user assets.
- Design every state: idle, pressed, selected, dragging, loading, empty, error, success, disabled, undo, and interrupted. Text and icons must remain legible at small sizes and with accessibility settings.
- Keep visual complexity concentrated in crafted objects; preserve enough breathing room for comprehension. Maximalist animation does **not** require a cluttered layout.

## 3. Multisensory interaction
- Coordinate animation, haptics and sound at the **same causal moment**. Support hardware-dependent haptic fallbacks and optional sound/mute preferences. Avoid excessive repeated pulses.
- Give tactile weight and meaningful feedback to manipulation, placement, folding, shaking, growth and completion; make interactions enjoyable, reversible where possible and forgiving of imprecise gestures.

## 4. Quality bar
- Review actual screenshots/recordings on target screen sizes and Android versions; inspect alignment, clipping, color, text, compositing, touch targets, animation timing and performance.
- Never infer design quality from a successful build or unit test. Visual QA is evidence-based; report screenshots/device runs separately from static inspection and CI.
- Reject visually inconsistent, mechanically awkward, unfinished or misleading states. Document design tradeoffs and unresolved device-only checks before calling a feature design-approved.

**Companion checklist:** `docs/DESIGN_QA.md`.

## Lab 4 — unassigned design brief
- No visual identity or product category is selected yet. Use these standards as quality gates once the user defines the concept; do not fabricate screens, materials or a design system in advance.
