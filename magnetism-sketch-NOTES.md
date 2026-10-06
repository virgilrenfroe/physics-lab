# Magnetism — fields, forces, and Faraday induction

## Education use
**High school / intro college physics: magnetic field direction, the force on a moving charge and on a current, the field of a bar magnet and of a long straight wire, and a first look at Faraday induction.**

Guided **12-step** lesson (Watch / Now on every step, try-it questions with hints):

1. **Meet the magnet** — north end warm, south end lilac, pearl test charge, short wire segment, coil waiting on the right. Outside the bar, field lines leave north and enter south.
2. **Right-hand rule** — straight wire. Thumb along the current, fingers curl with B. B = μ₀ I / (2π r).
3. **Field of the bar** — lines are the outside of closed loops. Closer lines near the poles mean a stronger field. The meter is the number. This model draws the outside of the bar. Inside a real magnet the field runs from south back to north.
4. **Force on a charge** — F = q v × B, so |F| = |q| v B sinθ. Lilac arrow is v, small honey arrow is B, warm arrow is F. Arrow length is a drawing scale. The meter is the true force.
5. **When the force is zero** — v along B, sinθ = 0, F = 0. Across the field, sinθ = 1 and the force is as large as |q| v B. The force is perpendicular to v, so it changes direction, not speed.
6. **Force on a wire** — F = I L × B, |F| = I L B sinθ. Same palm-push as the charge. The segment is a short piece of current.
7. **Double it** — |F| on the charge scales with speed. |F| on the segment scales with I. Around the long wire, B scales with I. Linear in those quantities, not an inverse square.
8. **A straight wire** — B = μ₀ I / (2π r). Double the distance and B halves. A single wire is a weak source next to the bar.
9. **Changing flux** — Φ through the 200-turn coil, emf = −N ΔΦ/Δt. A still magnet has emf = 0 even though B is not zero. Move closer and the emf leaves zero while the flux is changing.
10. **Lenz’s law** — the induced current makes a field that opposes the change. North pole approaching: the near face of the coil repels it. Pulling away reverses the current.
11. **In the real world** — an MRI technologist and a medical physicist in a hospital radiology suite, an electric-motor design engineer, a power-grid transformer technician in a substation, a maglev or rail engineer on a guideway.
12. **Questions** — eight hints (line direction, double the speed, velocity along B, ILB on the axis, wire field at 5 cm and 10 cm, why a steady flux induces nothing, Lenz direction, motor force versus an MRI field).

Chips and lesson buttons share one dispatcher: Bar magnet, Straight wire, Across, Along, Faster, Slower, Double I, Halve I, Flip q, Move closer, Move away, Reset, plus lesson acts that place the charge or the segment.

**Reset values.** Bar magnet, charge on the axis beyond the north pole, segment beside it, velocity across the field.

- Pole strength is chosen so the field at the axis point (x = 0.40 m, level with the poles) is exactly 5.00 mT. Poles sit 0.11 m either side of the bar’s center. The outside field is the intro two-pole picture: field leaves the north pole and enters the south pole. The interior of the bar is not part of the reading.
- q = +2.00 μC, v = 80 m/s, θ = 90°. |F| = |q| v B = 0.800 μN. Faster doubles the speed and doubles that force to 1.600 μN.
- Segment: I = 5.00 A, L = 0.10 m. On the axis, where B = 5.00 mT and the current is across the field, |F| = I L B = 2.50 mN. Flip q reverses only the charge.
- Straight wire: I = 20 A upward. At r = 5.0 cm, B = μ₀ I / (2π r) = 0.080 mT. At r = 10 cm, B = 0.040 mT. The force on the same charge there is 12.8 nN, which is the point of the comparison: one wire is a weak field.
- Coil: 200 turns, square 0.18 m on a side, resistance 5.0 Ω, standing to the right of the north pole. Flux is the average of Bₓ on a 3×3 grid across the loop, times the area. emf = −N ΔΦ/Δt while the bar moves. With the picture held still, Move closer jumps the bar 0.16 m toward the coil and spreads that change over 0.40 s, about −15 mV from the reset position. Move away gives a smaller emf of the opposite sign. When the bar is still, the emf is 0.

Bars on the right are logarithmic so a millitesla magnet and a microtesla wire both stay on the scale. The numbers are the true values. Arrow lengths are a drawing scale so the direction stays visible; they still grow when the force grows.

## What it shows (craft)
One WebGL scene, void `#140818`, pearl / warm `#ffb36b` / lilac `#b9a2ff`, with honey `#f0c24b` on the field-direction arrowheads. A bar magnet with warm field-line threads, a draggable test charge, a short current segment, a vertical wire with circular field lines, and a coil for the induction steps. Dragging empty space leans the view, and the view eases back. Solids, including the field threads and the wire circles, use MeshStandardMaterial.

## Controls
- Drag the pearl charge or the short segment across the bench. Drag the bar along its length.
- Chips and the lesson drive the same actions. ← → moves lesson steps.
- `?still` or reduced motion holds a readable still (lines, arrows, and meters drawn; arrowheads and coil beads do not travel). Move closer still reports an emf, using the 0.40 s change. `?embed` hides the chrome. `?nolesson` starts with the lesson collapsed.

## Constraints
- One `WebGLRenderer`, `setPixelRatio(Math.min(devicePixelRatio, 1.5))`.
- Local three r170 via `./vendor/three/build/three.module.js`.
- HemisphereLight plus one warm PointLight. No shadow maps. Solids use MeshStandardMaterial.
- RAF pauses on `document.hidden`. Teardown on `pagehide` (`window.__magnetismTeardown`).
- Test hook: `window.__magnetism.act(...)`, `.goStep(i)`, `.snapshot()`.

## Physics Lab
Lab home: [`index.html`](index.html). Siblings on this repo’s main line: [`newton-laws-sketch.html`](newton-laws-sketch.html), [`spring-orbit-sketch.html`](spring-orbit-sketch.html).
