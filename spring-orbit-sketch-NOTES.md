# Spring & Orbit — Hooke's law + orbital motion exhibit

## Education use
**High school / intro college physics: a lab visual for Hooke's law, damped oscillation, and gravitational orbits.**
- **Hooke's law & damping:** pull the mass, let go, and watch F = −kx − cv bring it back. *Light damping* (0.8 kg, ζ 0.08) overshoots and rings. *Heavy damping* (2.4 kg, ζ 0.60) hangs lower (static stretch mg/k) and settles in about one swing. The HUD gives spring constant k, mass m, damping c, damping ratio ζ = c / 2√(km), period T = 2π/ω_d, and live displacement x from equilibrium. A sparkline draws x(t) so the decaying envelope reads at a glance.
- **Orbital motion / gravity:** a pearl planet on an ellipse (e ≈ 0.45) and a lilac one on a near-circle around one central mass (a = −GM r̂/r²). Fling a planet: its new speed gives a new orbit, and the faint ellipse redraws live from the osculating elements. The HUD gives semi-major axis a, eccentricity e, period T = 2π√(a³/GM), r · speed v, and g = GM/r². **Kepler III:** both planets show the same T²/a³ (4π²/GM = 4.935). Speed it up past escape and the HUD reports *E ≥ 0 · escape speed exceeded*, then the planet respawns.
- **Momentum (bonus):** swing the spring mass into a planet. A soft sphere–sphere push trades momentum (restitution 0.45) and bumps the planet onto a new orbit.
- **Lesson panel (the explainer):** a 7-step guided lesson on the page, open by default. 1 Hooke's law (F = −kx, what k and x mean) · 2 Damping (light overshoots, heavy settles, ζ, T ≈ 2π√(m/k)) · 3 Why it hangs at Δ = mg/k · 4 Gravity & orbits (F = GMm/r², fall + miss = ellipse) · 5 Eccentricity · 6 Kepler III (why both planets share T²/a³ = 4π²/GM) · 7 Questions to try, with tap-to-open hints. Each step has a formula, a short plain-English explanation, a **Watch** line that points at the live scene, a **Now** line with live values (e.g. "x = −0.13 m → F = −kx = +3.62 N", or live T²/a³ next to 4π²/GM), and action buttons that drive the scene (Pluck, Light/Heavy, Push faster +12% / Slow down −12%, Reset orbit). The HUD column and in-scene tags for the topic that is not active dim so attention follows the lesson. Navigation: Back/Next, step dots, ← → keys. Desktop: a glass card under the title (*Hide* collapses it to a pill, and the spring shifts right so the card never covers it). Phones/portrait: a bottom sheet with **Learn | Numbers** tabs, Learn by default. `?nolesson` starts with the card collapsed.
- Classroom prompts: Why does the heavy mass hang lower? Which preset gets back to x = 0 first? Do T²/a³ for the two planets match? What speed makes the planet escape?
- Units: spring side in m, kg, s with g = 9.81. Orbit side in toy units (GM = 8 u³/s²). Every number is computed from the live state, none are canned.

## What it shows (craft)
One WebGL scene in Noctuary exhibit framing: void `#140818`, pearl type, warm `#ffb36b` / `#f0c24b` accents. Oversized Bricolage title, Instrument Sans subtitle, Space Mono HUD and in-scene tags (k, m, x = 0, GM). Behind it sits a soft night-city backdrop: one InstancedMesh of towers, twinkling window Points, and a warm horizon haze. The sun is the scene's single warm PointLight, with a HemisphereLight for fill. Materials are satin MeshStandard / MeshPhysical (clearcoat). Motion reads as a clip through additive ring-buffer glow trails.

## Controls
- **Drag the orange mass** to stretch/pluck the spring (3D elastic pendulum: axial spring plus pendulum swing), then release.
- **Drag/fling a planet** in its tilted orbit plane. The release velocity becomes the new orbit.
- **Drag empty space** to lean the camera gently. It eases back to the fixed exhibit framing (no OrbitControls fighting the picks).
- Chips: **Light damping / Heavy damping / Reset**. When nobody touches it for 7 s, the spring gets a soft auto-pluck so the exhibit keeps moving.
- `?still=1` or `prefers-reduced-motion` → the physics runs forward 2.2 s and freezes (a real snapshot with trails). Dragging still repositions the objects and redraws. `?embed=1` → transparent, no chrome or city. `?nobloom` → debug switch.

## Constraints honored
- One `WebGLRenderer` (the sparkline is a small 2D canvas, not WebGL). `setPixelRatio(Math.min(devicePixelRatio, 1.5))` on every device.
- Local three r170 via import map (`./vendor/three/...`). Subtle UnrealBloom on desktop only. Skipped on mobile, reduced-motion, and embed. The sun halo sprite keeps the glow without bloom.
- Spheres 32×24 desktop / 20×14 mobile, shared geometry. Coil is one TubeGeometry helix scaled to the live length (no per-frame rebuild). No shadow maps. No per-frame allocations in the loop.
- Physics: fixed 240 Hz substeps. Spring uses semi-implicit Euler, orbits use leapfrog (KDK, symplectic), so the ellipse stays closed.
- RAF pauses on `document.hidden`. `pagehide` teardown disposes geometry, materials, textures, composer, and renderer (`window.__springOrbitTeardown`).
- Portrait layout stacks the spring over the orbit. Landscape places them side by side.

## Physics Lab
Standalone **Physics Lab** classroom repo. Lab home: [`index.html`](index.html). Sibling: [`newton-laws-sketch.html`](newton-laws-sketch.html).
