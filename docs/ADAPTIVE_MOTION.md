# Motion architecture — superseded adaptive proposal

**Current binding strategy: [MOTION_FIRST_PLAN.md](MOTION_FIRST_PLAN.md).**

The previous generalized Adaptive Motion Engine proposal is **not approved for implementation**. Optimize the actual high-impact animations for the Motorola Moto G6 first, preserve maximalist design and consistent choreography, then validate on the Nothing Phone 3a. Only introduce narrow device-specific fallback when measured evidence warrants it.

Hardware/benchmark evidence: [MOTO_G6_REFERENCE.md](MOTO_G6_REFERENCE.md). Performance targets and test status: [PERFORMANCE_BUDGET.md](PERFORMANCE_BUDGET.md), [COMPATIBILITY_MATRIX.md](COMPATIBILITY_MATRIX.md).

Preserve touch priority, offscreen pause, reduced-motion accessibility, memory discipline, haptic semantics, gesture timing, persistence and future ZIMT portability. No dynamic quality tiers by default.
