# Momentum & collisions exhibit

## Education use
**High school / intro college physics: momentum p = mv, impulse J = FΔt = Δp, and conservation of momentum in collisions.**

Guided **11-step** lesson (Watch / Now on every step, try-it questions with hints):

1. **Meet the carts** — orange A, lilac B, thin velocity arrows, thick momentum arrows, a flash at impact.
2. **Momentum** — p = mv. Mass and speed each count once. Contrast with KE = ½mv².
3. **Impulse** — a 10 N push for 0.30 s delivers J = 3 N·s = Δp, if no end stop interrupts.
4. **Total momentum** — p total = pA + pB, signs included. Head-on equal speeds give 0.
5. **A collision conserves p** — internal impulses cancel. End stops are outside the system, so p total changes there and J records it.
6. **Elastic bounce** — e = 1. Relative separation matches approach. KE after matches KE before.
7. **Perfectly inelastic** — e = 0. Shared speed v = p total / (mA + mB). KE drops. Momentum still holds.
8. **Equal masses, target at rest** — bounce trades velocities. Stick leaves them at half speed and half KE.
9. **Unequal masses** — light A into heavy B (3 kg). A can rebound. p total still matches the incoming pA.
10. **Check both sides** — the line p − p₀ − J stays near 0. KE is what tells bounce from stick.
11. **Questions** — eight hints (p vs KE, the 3 N·s push, equal-mass trade, stick and half KE, head-on zero, why the end stop counts, light-into-heavy, push then collide).

Chips and lesson buttons share one dispatcher: Launch · Bounce/Stick · Mass A · Mass B · Reset · Push A · Push B · Heavy · Equal · Head-on.

Units: SI (kg, m/s, kg·m/s, N·s, J). The air track has no friction, so between pushes, hits, and end stops, p total is constant. p₀ is total momentum at the last launch, reset, mass change, or placement. J sums external impulse only.

Placing a cart or changing mass starts that check again. A velocity you did not push or collide would break p − p₀ − J = 0.

## What it shows (craft)
One WebGL scene, Noctuary void `#140818`, pearl / warm `#ffb36b` / honey `#f0c24b` / lilac `#b9a2ff`. A level air track, two carts, velocity and momentum arrows, a contact flash, and a gold link when they stick. Honey and lilac columns compare p total with p₀ + J. Lesson slab and chips keep the lab’s weighted chrome: hard offset, no rounded card, press that shortens, then settles. A hit shoves the title and the meters along the momentum transfer and eases back; the carts compress on contact. Reduced motion keeps the pose and skips that travel.

## Controls
- Drag a cart to place it (that cart’s velocity goes to 0, and the momentum check starts again).
- Chips / lesson acts drive the scene. ← → lesson steps.
- `?still` / reduced-motion · `?embed` · `?nolesson`.
- Phones: Learn | Numbers sheet.

## Constraints
- One `WebGLRenderer`, `setPixelRatio(Math.min(dpr, 1.5))`.
- Local three r170 via `./vendor/three/...`.
- Fixed 240 Hz substeps. Collision uses the 1D formulas with e = 1 (bounce) or e = 0 (stick). Wall reversal adds J = Δp so p − p₀ − J still holds.
- Teardown on `pagehide` (`window.__momentumTeardown`).
- Test hook: `window.__momentum.act('launch'|'stick'|'bounce'|'push-a'|'heavy'|'meet'|…)` , `.step(n)`, and `.state`.
