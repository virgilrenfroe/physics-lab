# Electrostatics — Coulomb’s law, electric field, and potential

## Education use
**High school / intro college physics: Coulomb’s law, the electric field, superposition, and electric potential for point charges.**

Guided **12-step** lesson (Watch / Now on every step, try-it questions with hints):

1. **Meet the charges** — amber positive, lilac negative, pearl probe. F = k|qA qB|/r² with k = 8.99 × 10⁹.
2. **Attract or repel** — same signs repel, opposite signs attract. Warm arrows show the pair force.
3. **What an electric field is** — E = F/q0, force per unit positive test charge. Gold arrow on the probe.
4. **Field lines** — honey threads. Tangent is E. Lines leave +, end on −, and do not cross. Closer lines mean a stronger field. The meter is the number.
5. **Superposition** — turn on charge C. Thinner arrows are each charge’s field. The thick gold arrow is the vector sum.
6. **Potential** — V = kq/r with V = 0 far away. Potentials add as numbers. ΔU = q0 ΔV. Static charges only: no circuits, no changing magnetic fields.
7. **Equipotentials** — lilac curves of constant V. The field points toward lower V and crosses the curves. Closer curves mean a larger |E|.
8. **Double the charge** — one charge doubled doubles F and doubles that charge’s |E| and V. Both charges doubled would multiply F by four.
9. **Double the distance** — F and |E| follow 1/r². V of a point charge follows 1/r.
10. **Arrow convention** — arrows follow a positive test charge. A neutral object feels no net Coulomb force.
11. **In the real world** — air ionizes near 3×10⁶ V/m. An electrical engineer sizing high-voltage clearances, an ESD engineer protecting chips, a weather scientist or lightning-safety planner thinking about charge separation.
12. **Questions** — eight hints (predict F, double q, double r, midpoint of a dipole, why lines do not cross, arrow convention, neutral scrap, where |E| is strongest).

Chips and lesson buttons share one dispatcher: Flip sign, Double q, Halve q, Double r, Third charge, Equipotentials, Reset, plus lesson acts (Same signs, Opposite signs, Equal dipole, probe placements, Select A/B/C).

Units: SI. Charges are shown in microcoulombs. Every number is computed from the live charges. Arrow lengths on the table are a drawing scale so direction stays visible. The meters carry the true F, |E|, and V.

## What it shows (craft)
One WebGL scene, void `#140818`, pearl / warm `#ffb36b` / honey `#f0c24b` / lilac `#b9a2ff`. A round table in the dark, honey field-line threads with arrowheads that drift along the field, lilac equipotential curves, and a draggable probe. Dragging empty space leans the view and the view eases back with a little weight. Charge spheres use MeshStandardMaterial and lift slightly while grabbed.

## Controls
- Drag charge A, B, or C (when C is on). Drag the pearl probe to move the measurement point.
- Drag empty space to lean the table. It settles back.
- Chips and the lesson drive the same actions. ← → moves lesson steps.
- `?still` or reduced motion holds a readable still (field lines, curves, and meters drawn; arrowheads do not travel). Dragging still updates the picture. `?embed` hides the chrome. `?nolesson` starts with the lesson collapsed.

## Constraints
- One `WebGLRenderer`, `setPixelRatio(Math.min(devicePixelRatio, 1.5))`.
- Local three r170 via `./vendor/three/build/three.module.js`.
- HemisphereLight plus one warm PointLight. No shadow maps. Solids use MeshStandardMaterial.
- RAF pauses on `document.hidden`. Teardown on `pagehide` (`window.__electrostaticsTeardown`).
- Test hook: `window.__electrostatics.act(...)`, `.goStep(i)`, `.snapshot()`.

## Physics Lab
Lab home: [`index.html`](index.html). Siblings on this repo’s main line: [`newton-laws-sketch.html`](newton-laws-sketch.html), [`spring-orbit-sketch.html`](spring-orbit-sketch.html).
