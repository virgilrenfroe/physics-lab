# Circular motion — centripetal force exhibit

## Education use
**High school / intro college physics: uniform circular motion and centripetal force.**

A mass on a string, whirling in a horizontal circle around a fixed peg. The floor is a measured stage (it does not spin). The string is the force. Curriculum is on the page before the lesson opens:

**a<sub>c</sub> = v²/r** &nbsp;&nbsp; **F<sub>c</sub> = mv²/r** &nbsp;(also **a<sub>c</sub> = ω²r**, **F<sub>c</sub> = mω²r**)

Guided **11-step** lesson (Watch / Now on every step, try-it questions with hints):

1. **Meet the mass** — lilac v tangent, honey a<sub>c</sub> toward the peg, string = F<sub>c</sub>. Right angle at the mass.
2. **Uniform circular motion** — speed constant, direction of v changes.
3. **Radius r** — drag the mass; the string length is r. Floor rings at 0.40 / 0.80 / 1.20 / 1.60 m.
4. **Period and frequency** — T = 2πr/v, f = 1/T. Lap tick on the rim.
5. **Angular speed** — ω = v/r. Live check that v²/r and ω²r match.
6. **Centripetal acceleration** — a<sub>c</sub> = v²/r, inward, even though speed is steady.
7. **Why inward** — inertia wants the straight tangent; the string bends the path toward the center. Faint “if the string snapped” arrow.
8. **Centripetal force** — F<sub>c</sub> = ma<sub>c</sub> = mv²/r = mω²r. The string. No outward force in this lab frame.
9. **Double v** — a<sub>c</sub> and F<sub>c</sub> ×4 (v²), r and m fixed.
10. **Change r or m** — double r at fixed v → a<sub>c</sub> halves. Double m at fixed v and r → a<sub>c</sub> unchanged, F<sub>c</sub> doubles. The ball grows with m.
11. **Questions** — eight hints, including a live check that a<sub>c</sub> equals both v²/r and ω²r.

Chips and lesson buttons share one dispatcher: Faster · Slower · Double v · Halve v · Double r · Halve r · Wider · Tighter · Double m · Halve m · Reset.

**Reset values (exact):** r = 0.80 m, v = 1.20 m/s, m = 0.50 kg → ω = 1.50 rad/s, a<sub>c</sub> = 1.80 m/s², F<sub>c</sub> = 0.90 N, T = 4.19 s. Every number on the page is computed from the live state.

Units: SI (m, m/s, rad/s, m/s², N, kg, s). Dragging the mass sets r and the angle; **v is held fixed**, so a<sub>c</sub> = v²/r updates immediately.

## What it shows (craft)
One WebGL scene. Physics Lab void `#140818`, pearl type, warm `#ffb36b` / honey `#f0c24b` / lilac `#b9a2ff`. Oversized asymmetric Bricolage title (*Circular* / light *motion*), Instrument Sans lesson, Space Mono for the formula lockup, meters, and in-scene tags.

The teaching picture is the classic right angle: tangent velocity, inward acceleration, string along the radius. A warm wake follows the mass. Empty-space drag tilts the stage and eases back.

### YES references (subject fit)
- **[penguin.music](https://penguin.music/)** — motion is the subject. The orbit is a living wake, not a stroked diagram: the mass leaves a warm trail so uniform motion reads as something ongoing.
- **[TILToooTILT](https://tiltoootilt.tote.co.jp/)** — weight. The ball grows with m, the string brightens and thickens with F<sub>c</sub>, and dragging empty space tilts the stage with a heavy ease-back. Force is a property of the object in the scene. Chrome is oversized type, not a card grid.
- **[Persona Studio](https://www.csswinner.com/details/persona-studio/19388)** — the city-as-volume idea, used quietly. The circle sits in a three-quarter space (you can tilt it), with faint orbital lines in the void. It is an apparatus you look into, not a top-down worksheet.

Set aside for this exhibit: Bearplus, nexstudio.tech, rubenmarcus.dev, Loop Agency, Why Zero. Those read as studio or editorial chrome. This page needs an orbit a teacher recognizes, plus weight on the mass. No SaaS shell, no dark-and-cream card grid.

## Controls
- **Drag the mass** to set the string length r (and pose the angle). Speed v stays put.
- **Drag empty space** to tilt the stage. It eases back.
- Chips: **Faster / Slower / Double v / Double m / Reset**.
- Lesson: Back / Next, step dots, ← → keys. Desktop: glass card under the title (*Hide* collapses it to a pill). Phones: bottom sheet with **Learn | Numbers**.
- Query flags (not shown in the learner chrome): `?embed` transparent, no chrome. `?still` or `prefers-reduced-motion` freezes a composed frame (drag still repositions and redraws). `?nolesson` starts with the card collapsed.

## Constraints honored
- One `WebGLRenderer`. `setPixelRatio(Math.min(devicePixelRatio, 1.5))`.
- Local three r170 via `./vendor/three/build/three.module.js` only.
- Lights: `HemisphereLight` + one warm `PointLight`. Apparatus materials are `MeshStandardMaterial`. Teaching arrows are flat `MeshBasicMaterial` so the vectors stay readable. No shadow maps. No bloom pass.
- Angle is integrated as θ += (v/r) dt (fixed 240 Hz slices, capped per frame) so the radius cannot drift the way a Cartesian integrator would. While the mass is dragged, θ follows the pointer and v is unchanged.
- Trail is a fixed ring buffer (no per-frame allocations).
- RAF pauses on `document.hidden`. `pagehide` teardown disposes geometries, materials, textures, and the renderer (`window.__circularMotionTeardown`).
- Test hook: `window.__circularMotion` with `.state`, `.act('double-v'|…)`, `.goStep(i)`, `.step`, `.still`. `window.__circularMotionReady` when the scene is up.

## Physics Lab
Lab home: [`index.html`](index.html). Siblings on this branch’s base: [`spring-orbit-sketch.html`](spring-orbit-sketch.html), [`newton-laws-sketch.html`](newton-laws-sketch.html).
