# Waves on a string — transverse wave exhibit

## Education use
**High school / intro college physics: a lab visual for a transverse wave on a rope.**

The page is titled as a classroom exhibit. Curriculum is on screen the whole time: **v = fλ** and **v = √(T/μ)**, with live SI meters for amplitude A, frequency f, wavelength λ, speed v, tension T, and linear density μ.

Guided **11-step** lesson (Watch / Now on every step):

1. **Meet the rope** — 4.00 m between two posts. The rope moves up and down; the pattern travels toward the pulley. The brass weight is the tension.
2. **Amplitude A** — max displacement from the center line, in meters. Drag the rope. A does not change v.
3. **Wavelength λ** — crest to crest. The bracket marks one λ when it fits. If λ is longer than the rope, the bracket marks L instead (on the 1st harmonic it reads L = λ/2).
4. **Frequency f** — crests per second. Period is shown as 1/f so the letter T stays tension.
5. **Wave speed v = fλ** — faster driver, shorter wavelength, same speed. Table dashes travel at v and loop.
6. **Tension T** — the hanging weight. v = √(T/μ). Doubling T multiplies v by √2, not by 2.
7. **Linear density μ** — mass per meter of the rope, not the hanging weight. Heavier rope, slower wave. The rope thickens as μ rises.
8. **Both formulas** — fλ and √(T/μ) are computed separately and should match.
9. **Traveling wave** — y = A sin(2πx/λ − 2πft). The crest moves; a piece of rope does not.
10. **Standing wave** — fixed ends, nodes and antinodes. 2nd harmonic: 3 nodes (count the posts), 2 antinodes.
11. **Harmonics and questions** — λ_n = 2L/n, f_n = nv/(2L). Tighten on a standing wave and λ stays, f rises. Nine try-it questions with hints.

Chips and lesson buttons share one dispatcher: Travel · 1st · 2nd · 3rd · Faster · Slower · T ×2 · T ÷2 · μ ×2 · μ ÷2 · Reset, plus Louder / Softer in the lesson. Drag the rope to set A.

Units: meters, hertz, m/s, newtons, kg/m. Opening numbers are exact: T = 2.40 N, μ = 0.150 kg/m, v = √(T/μ) = 4.00 m/s, f = 2.00 Hz, λ = 2.00 m. Every number is computed from the live state.

Ideal model, stated for class: no sag, constant tension, and the traveling wave is the steady driven shape (not a reflected pulse). The hanging weight shows T; it does not bounce. On a standing wave the ends are nodes. A in the standing formula is the antinode displacement you see (some textbooks write 2A when each of the two traveling waves has amplitude A).

## What it shows (craft)
One WebGL scene, void `#140818`, pearl type, warm `#ffb36b` / honey `#f0c24b` / lilac `#b9a2ff`. Bricolage Grotesque title, Instrument Sans lesson, Space Mono meters (Greek marks set in Instrument Sans).

Subject-fit references, not a general restyle:

- **penguin.music** — the rope is the visualizer. Crests shift from pearl to honey, troughs toward lilac, and the single warm point light rides a crest.
- **Loop** — the traveling wave does not restart as a clip. Phase keeps running, and the speed dashes loop along the table at v.
- **Persona** (spatial) — two posts, a table, a pulley, and a little fog. Drag empty space and the camera leans, then settles. A few quiet masses sit back in the fog so the rope is in a place, not on a worksheet.
- **tiltoootilt** — weight. The brass mass grows with T. Dragging the rope lags more when tension is low and catches up when the rope is tight. The lesson card is a heavy glass slab.

Not used: Bearplus, nexstudio.tech, rubenmarcus.dev, Why Zero (type and layout studios; this exhibit is led by the moving rope). No SaaS shell, no dark-and-cream cards.

## Controls
- **Drag the rope** vertically to set amplitude. The rope eases toward your hand; higher tension follows faster.
- **Drag empty space** to lean the camera. It eases back.
- Chips and the lesson drive the same actions. ← → steps the lesson.
- Desktop: lesson card under the title (Hide collapses it). Phones: bottom sheet with Learn | Numbers.

## Query flags
Documented here only. They are not printed in the learner chrome.

- `?still` or `prefers-reduced-motion: reduce` — phase freezes at a readable crest (traveling) or at full antinode displacement (standing). Dragging still updates the picture.
- `?embed` — transparent page, no chrome, lesson, vignette, or tags. One canvas for a host page.
- `?nolesson` — lesson starts collapsed (desktop).

## Constraints honored
- One `WebGLRenderer`. `setPixelRatio(Math.min(devicePixelRatio, 1.5))`.
- Local three r170 via `./vendor/three/build/three.module.js` only.
- Lights: `HemisphereLight` plus one warm `PointLight`. Materials are `MeshStandardMaterial` (reference lines use `LineBasicMaterial`).
- Rope positions update in place. Normals are recomputed with reused vectors. No shadow maps.
- RAF pauses on `document.hidden`. `pagehide` teardown disposes geometries, materials, and the renderer.
- Hooks: `window.__wavesString` (`state`, `act`, `goStep`, `sample`, `metrics`, `still`) and `window.__wavesStringTeardown`. `window.__wavesStringReady` is set after boot.

## Physics Lab
Lab home: [`index.html`](index.html). Siblings on main: [`spring-orbit-sketch.html`](spring-orbit-sketch.html), [`newton-laws-sketch.html`](newton-laws-sketch.html).
