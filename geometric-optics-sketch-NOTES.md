# Geometric optics — mirrors, thin lenses, and ray traces

## Education use
**High school / intro college physics: reflection, refraction (Snell’s law), and image formation by thin lenses and spherical mirrors.**

Guided **12-step** lesson (Watch / Now on every step, try-it questions with hints):

1. **Meet the bench** — object arrow, thin lens, optical axis. The meters are object distance d_o, image distance d_i, focal length f, and magnification m.
2. **Reflection** — angle of incidence equals angle of reflection, measured from the normal. A mirror sends the ray back.
3. **Refraction and Snell** — n₁ sin θ₁ = n₂ sin θ₂. Air n = 1.00, glass n = 1.50. The ray bends toward the normal entering glass, and away leaving it. Steep enough, and the ray inside the glass reflects completely.
4. **Thin-lens equation** — 1/f = 1/d_o + 1/d_i, same unit on every term. Centimeters on this bench. The same equation is used for spherical mirrors.
5. **Three principal rays** — parallel ray through the far focal point, ray through the center, ray through the near focal point. They meet at the image. On a mirror: parallel through the focal point, vertex ray with equal angles, ray through the focal point reflected parallel. A ray through the center of curvature reverses.
6. **Real image** — object beyond the focal point of a converging lens. Rays meet on the far side. The image is inverted. At 2f, it is the same size and also at 2f.
7. **Virtual image** — object inside the focal length. Rays only appear to meet on the object’s side. Upright and enlarged. A magnifier works this way. A card on the far side stays dark.
8. **Magnification** — m = −d_i / d_o. Negative means inverted. |m| > 1 means larger than the object.
9. **Diverging lens** — f is negative. For a real object the image is virtual, upright, and smaller, on the object’s side.
10. **Mirrors** — a concave mirror can form a real inverted image in front, or a virtual upright image behind when the object is inside the focal length. A convex mirror, for a real object, forms a virtual upright smaller image behind the mirror.
11. **In the real world** — lens power in diopters is 1/f with f in meters. An optometrist and an ophthalmic technician fitting glasses in an exam lane or optical shop. A camera engineer and an optical engineer designing lenses for augmented-reality glasses. A stage-lighting designer and a lighthouse-lantern designer sending a beam from a lamp near a focus. A telescope optician focusing parallel starlight to a real image.
12. **Questions** — eight hints (image at 2f, double f, object inside f, why m is negative, a diverging lens, Snell’s bend, why a card catches only a real image, a convex passenger-side mirror).

Chips and lesson buttons share one dispatcher: Change type, Double f, Halve f, Flip side, Move object, Reset, plus lesson acts (converging, diverging, concave, convex, place at 2f, between f and 2f, inside f, at the focal point, beyond 2f, glass surface, steeper, shallower, reverse the ray, show the center-of-curvature ray).

**Sign convention used on the bench.** Light comes from the object toward the lens or the reflecting face. d_o is positive. f is positive for a converging lens and a concave mirror, and negative for a diverging lens and a convex mirror. d_i is positive for a real image (far side of a lens, in front of a mirror) and negative for a virtual image. m = −d_i / d_o.

Units: centimeters on the meters, from distances stored in meters. Every number is computed from the live object distance and focal length. If an image is extremely tall, the arrow is shortened so it stays in view, and the magnification meter keeps the true value. Ray arrowheads are a drawing scale so the direction stays visible.

## What it shows (craft)
One WebGL scene, void `#140818`, pearl / warm `#ffb36b` / lilac `#b9a2ff`. An optical bench in the dark: upright object arrow, thin converging or diverging lens (or a concave or convex mirror), three principal rays, and the real or virtual image. Focal points sit on the axis. A glass surface can replace the bench for Snell’s law, with the incident, reflected, and refracted rays. Dragging empty space leans the view, and the view eases back with a little weight. Solids use MeshStandardMaterial.

## Controls
- Drag the object arrow along the bench to change d_o.
- On the glass surface, drag the ray handle to change the angle from the normal.
- Drag empty space to lean the view. It settles back.
- Chips and the lesson drive the same actions. ← → moves lesson steps.
- `?still` or reduced motion holds a readable still (rays, arrows, and meters drawn). Dragging still updates the picture. `?embed` hides the chrome. `?nolesson` starts with the lesson collapsed.

## Constraints
- One `WebGLRenderer`, `setPixelRatio(Math.min(devicePixelRatio, 1.5))`.
- Local three r170 via `./vendor/three/build/three.module.js`.
- HemisphereLight plus one warm PointLight. No shadow maps. Solids use MeshStandardMaterial.
- RAF pauses on `document.hidden`. Teardown on `pagehide` (`window.__geometricOpticsTeardown`).
- Test hook: `window.__geometricOptics.act(...)`, `.goStep(i)`, `.snapshot()`.

## Physics Lab
Lab home: [`index.html`](index.html). Siblings on this repo’s main line: [`newton-laws-sketch.html`](newton-laws-sketch.html), [`spring-orbit-sketch.html`](spring-orbit-sketch.html).
