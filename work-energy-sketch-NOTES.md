# Work & energy — work–energy theorem exhibit

## Education use
**High school / intro college physics: work W = F·d, kinetic energy KE = ½mv², the work–energy theorem ΔKE = W_net, and gravitational potential energy PE = mgh.**

Guided **11-step** lesson (slower pace, Watch / Now on every step, try-it questions with hints):

1. **Meet the block** — orange F along the track, gold Δs, honey W_net and lilac ΔKE on the same scale (bars + trace).
2. **What work means** — W = F·d, force along the displacement. Normal force does no work. While F is steady, W_app matches F·Δs.
3. **Positive work** — push in the direction of motion, W > 0, speed and KE rise.
4. **Kinetic energy** — KE = ½mv², live. Change mass (1 → 2 → 4 kg). Books re-zero so the theorem stays fair.
5. **Work–energy theorem** — ΔKE = W_net. The equation line is the gap and should stay near 0 J.
6. **Coasting, W = 0** — flat track, F = 0, no friction. KE constant. Books zero at release so ΔKE stays 0.
7. **Negative work** — friction (μ = 0.22) and a backward pull. W_fric < 0, mechanical energy leaves, and ΔKE still equals W_net.
8. **Gravitational PE** — PE = mgh, g = 9.81. Raise the block; h is height above the low end.
9. **PE ↔ KE** — drop with friction off. PE falls, KE rises. Gravity as work: ΔKE = W_net. Gravity as PE: KE + PE holds.
10. **Check both sides** — add W_app + W_fric + W_grav + W_stop and compare with ΔKE.
11. **Questions** — eight hints (steady W = Fd, ½mv², why friction still matches, coast, sign of W_fric, normal force, drop, double m).

Chips and lesson buttons share one dispatcher: Apply force · Drop · Friction · Mass · Reset · Coast · Zero F · Raise PE · Pull · Halve F · Flat.

Units: SI (N, J, m, kg, m/s), g = 9.81. Every number is from live state. Spring energy ½kx² stays on the Hooke exhibit; this one stops at mgh.

Placing the block, changing mass, Coast, Raise, and Drop re-zero the work ledger on purpose. A velocity you did not integrate would break ΔKE = W_net, so those setups start a new check instead of inventing work.

## What it shows (craft)
One WebGL scene, Noctuary void `#140818`, pearl / warm `#ffb36b` / honey `#f0c24b` / lilac `#b9a2ff` / teal friction. A flat track that can become a ramp. Large labeled F arrow, displacement bar, height ruler, and a honey/lilac pair for W_net vs ΔKE. Lesson slab and chips use the lab’s weighted chrome (press settles, panel drops in). Soft solids, no city skyline.

## Controls
- Drag the force handle → F along the track. Drag the block → place it (books re-zero).
- Chips / lesson acts drive the sim. ← → lesson steps.
- `?still` / reduced-motion · `?embed` · `?nolesson`.
- Phones: Learn | Numbers sheet.

## Constraints
- One `WebGLRenderer`, `setPixelRatio(Math.min(dpr, 1.5))`.
- Local three r170 via `./vendor/three/...`.
- Fixed 240 Hz substeps. Work is booked with the same displacement the integrator uses, so ΔKE = W_net holds in exact arithmetic. A bumper bounce keeps a fraction of the speed and books the lost kinetic energy as W_stop.
- Teardown on `pagehide` (`window.__workEnergyTeardown`).
- Test hook: `window.__workEnergy.act('push'|'drop'|'friction'|'mass'|'coast'|…)` , `.step(n)`, and `.state`.
