# Newton’s laws — force, mass, acceleration exhibit

## Education use
**High school / intro college physics: a lab visual for Newton’s 1st, 2nd, and 3rd laws, net force, and a = ΣF / m.**
- **1st law (inertia):** if ΣF = 0, acceleration is zero and velocity stays constant. Coast with F_app = 0 and friction off — the cart keeps its speed. Mass is the measure of inertia.
- **2nd law:** ΣF = m · a, or a = ΣF / m. Live HUD and lesson **Now** lines show F_app, F_fric, ΣF, m, a, v, x. Drag the warm force handle to set F_app; drag the cart (when nearly still) to change m. The lilac arrow is a; the warm arrow is F_app.
- **Net force:** ΣF = F_app + F_fric. Optional kinetic friction μ = 0.25; from rest the cart stays stuck until |F_app| > μmg. Pearl friction arrow appears opposite v.
- **Double F / Double m:** with m fixed, doubling ΣF doubles a. With F fixed, doubling m halves a. Lesson buttons and chips drive both demos.
- **3rd law (action–reaction):** the hand pushes the cart with F_app; the cart pushes the hand with −F_app. Honey reaction arrow on the lilac push plate. The pair does **not** cancel on the cart — the reaction acts on the hand.
- **Lesson panel (the explainer):** 7-step guided lesson, open by default. 1 Inertia · 2 F = ma · 3 Net force & friction · 4 Double F · 5 Double m · 6 Action–reaction pair · 7 Questions with tap-to-open hints. Each step has a formula, plain-English explanation, a **Watch** line tied to the scene, a **Now** line with live ΣF / m / a (and pair forces on step 6), and action buttons (Apply push, Double F, Double m, Coast, Toggle friction, Reset). Navigation: Back/Next, step dots, ← → keys. Desktop: glass card under the title (*Hide* collapses to a pill). Phones/portrait: bottom sheet with **Learn | Numbers** tabs. `?nolesson` starts collapsed.
- Classroom prompts: If ΣF = 0 and the cart is moving, what is a? F = 4 N, m = 2 kg — what is a? Double F and m together — does a change? Why doesn’t the 3rd-law pair cancel the cart’s a? With μ = 0.25 and m = 1 kg, how large must F_app be to start from rest?
- Units: SI (N, kg, m, s) with g = 9.81. Every number is computed from the live state.

## What it shows (craft)
One WebGL scene in Noctuary exhibit framing: void `#140818`, pearl type, warm `#ffb36b` / `#f0c24b` / lilac `#b9a2ff` accents. Oversized Bricolage title, Instrument Sans subtitle, Space Mono HUD and in-scene tags (F_app, a, v, action ↔ reaction). Soft night-city backdrop (InstancedMesh towers + twinkling window Points + warm horizon haze). Satin MeshPhysical cart on a two-rail track with sleepers and soft bumpers. Additive glow trail on the cart. Force handle is a warm emissive sphere; push plate is lilac for the reaction pair.

## Controls
- **Drag the force handle** to set F_app (distance from cart × side = magnitude × sign).
- **Drag the cart** when nearly still (and F small) to change mass; otherwise reposition on the track.
- **Chips:** Apply push · Double F · Double m · Friction on/off (μ 0.25) · Reset.
- **Drag empty space** to lean the camera; it eases back.
- `?still=1` or `prefers-reduced-motion` → physics runs ~1.6 s then freezes (real snapshot). Dragging still updates numbers. `?embed=1` → transparent, no chrome/city/lesson. `?nolesson` → lesson starts closed.

## Constraints honored
- One `WebGLRenderer`. `setPixelRatio(Math.min(devicePixelRatio, 1.5))`.
- Local three r170 via import map (`./vendor/three/...`). Subtle UnrealBloom on desktop only (skipped on mobile, reduced-motion, embed).
- Shared geometries; no shadow maps; no per-frame allocations in the hot path beyond trail ring-buffer writes.
- Physics: fixed 240 Hz substeps, semi-implicit Euler. Soft bumper restitution at track ends.
- RAF pauses on `document.hidden`. `pagehide` teardown (`window.__newtonLawsTeardown`).
