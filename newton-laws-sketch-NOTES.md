# Newton’s laws — force, mass, acceleration exhibit

## Education use
**High school / intro college physics: Newton’s 1st, 2nd, and 3rd laws; net force; a = ΣF / m.**

Guided **12-step** lesson (slower pace, Watch / Now on every step, many try-it questions with hints):

1. **Meet the cart** — orange F_app, teal F_fric, thick gold ΣF, lilac a, mass block m; live meter bars.
2. **1st law (inertia)** — ΣF = 0 → a = 0 → v constant. Coast with F→0.
3. **What force means** — size + direction; drag handle; Double / Halve F.
4. **2nd law** — a = ΣF / m; equation line under meters always live.
5. **Net force** — ΣF = F_app + F_fric; gold arrow is what matches a.
6. **Friction** — μ = 0.25; stuck until |F_app| > μmg; teal arrow opposite v.
7. **Double F** — m fixed → a doubles (friction off for a clean check).
8. **Double m** — ΣF fixed → a halves; mass block grows.
9. **3rd law** — F on cart = −F on hand; reaction on lilac plate; pair does not cancel on the cart.
10. **Put it together** — short button sequence lab.
11. **In the real world** — seat belts and airbags (automotive safety engineer: more stopping time, smaller a = ΣF/m) and a sprint start (coach: action–reaction, larger ΣF or smaller m).
12. **Questions** — eight hints (predict a, double both, why pairs don’t cancel, μmg threshold, live ΣF/m check, …).

Chips and lesson buttons share one dispatcher: Apply push · Double F · Double m · Friction · Reset · Coast · Halve F · Zero F.

Units: SI (N, kg, m, s), g = 9.81. Every number is from live state.

## What it shows (craft)
One WebGL scene, Noctuary void `#140818`, pearl / warm `#ffb36b` / honey `#f0c24b` / lilac `#b9a2ff` / teal friction. Large labeled teaching arrows + HTML tags + meter bars for F_app, F_fric, ΣF, m, a. Simple high-contrast track; soft towers only (not a busy city). Mass shown as a growing gold block on the cart.

## Controls
- Drag force handle → F_app. Drag cart when nearly still → mass.
- Chips / lesson acts drive the sim. ← → lesson steps.
- `?still` / reduced-motion · `?embed` · `?nolesson`.

## Constraints
- One `WebGLRenderer`, `setPixelRatio(Math.min(dpr, 1.5))`.
- Local three r170 via `./vendor/three/...`.
- Fixed 240 Hz substeps. Teardown on `pagehide` (`window.__newtonLawsTeardown`).
- Test hook: `window.__newtonLaws.act('push'|'double-f'|…)` and `.state`.
