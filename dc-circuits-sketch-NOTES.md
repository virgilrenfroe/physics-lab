# DC circuits — Ohm’s law, series and parallel

## Education use
**High school / intro college physics: voltage, current, resistance, Ohm’s law, series and parallel circuits, equivalent resistance, and electric power.**

Guided **12-step** lesson (Watch / Now on every step, try-it questions with hints):

1. **Meet the circuit** — battery, two clear resistor blocks, wires, an ammeter in the loop, and a voltmeter you can move. The meters name V, I, R₁, R₂, R_eq, and P.
2. **Voltage, current, resistance** — voltage is energy per charge from the battery, current is charge per second past a point, resistance is how strongly a block opposes that. Units: volt, ampere, ohm.
3. **Ohm’s law** — V = I R. For the whole board, V = I R_eq. The equation under the meters uses the live numbers.
4. **Steady current** — the warm beads circulate. They keep their spacing, pass through the resistors, and return. Charge is not used up. The direction drawn is conventional current, from the positive terminal around to the negative terminal. Electrons in the metal drift the other way. The ammeter reads the same current either way.
5. **Series** — one path. The current is the same in both resistors. R_eq = R₁ + R₂. The voltages add: V = V₁ + V₂. The larger resistance takes the larger share of the voltage.
6. **Parallel** — two paths. The voltage across each resistor equals the battery. The currents add: I = I₁ + I₂. 1/R_eq = 1/R₁ + 1/R₂. The smaller resistance carries the larger current. On the shared wire, beads from both paths travel together, so that wire looks busier. A resistor does not swallow them.
7. **Equivalent resistance** — one resistor that would draw the same total current from the same battery. Series R_eq is larger than either resistor. Parallel R_eq is smaller than either resistor, so the same battery draws more total current.
8. **Double one resistance** — Double R changes the selected resistor (R₁ at reset). Doubling one resistor does not double R_eq, because the other resistor is still there. In series the current falls, and the doubled resistor takes a larger share of the voltage. In parallel, only that branch’s current changes.
9. **Change the voltage** — Raise V and Halve R. Resistances stay put when only V changes, and the current scales with V. Halving a resistance increases the current.
10. **Power** — P = I V for the whole circuit. For one resistor, P = I² R = V² / R. In series the larger resistance warms more. In parallel the smaller resistance warms more. The glow is energy leaving as heat each second. The beads are still in the loop.
11. **In the real world** — where the idea shows up, and jobs that use it. An electrician doing residential wiring (outlets in parallel on a branch, breaker sized for the sum of the currents). An electronics technician troubleshooting a board (a series string as a voltage divider, voltmeter across one part). An EV battery pack engineer balancing cells (series adds voltage, parallel groups add current). An appliance design engineer sizing a heater (a toaster element or dryer coil, P = I V).
12. **Questions** — eight hints (predict I, double R₁ in series, parallel versus series, double R₂ in parallel, why the beads do not pile up, what Raise V changes, which block glows, lamp and toaster in a kitchen).

Chips and lesson buttons share one dispatcher: Series, Parallel, Using R₁ / R₂, Double R, Halve R, Raise V, Reset, plus lesson acts (Lower V, Use R₁, Use R₂, voltmeter on the battery, on R₁, or on R₂).

**Reset values.** V = 12 V, R₁ = 10 Ω, R₂ = 20 Ω, series.

- Series: R_eq = 30 Ω, I = 0.400 A, V₁ = 4.00 V, V₂ = 8.00 V, P = 4.80 W (P₁ = 1.60 W, P₂ = 3.20 W).
- Parallel: R_eq = 6.67 Ω, I₁ = 1.200 A, I₂ = 0.600 A, I = 1.800 A, V₁ = V₂ = 12 V, P = 21.6 W (P₁ = 14.4 W, P₂ = 7.20 W).
- Series, after Double R on R₁: R₁ = 20 Ω, R_eq = 40 Ω, I = 0.300 A, V₁ = V₂ = 6.00 V.
- Parallel, after Double R on R₂: R₂ = 40 Ω, I₁ = 1.200 A, I₂ = 0.300 A, I = 1.500 A.

The ammeter and the voltmeter are ideal: the ammeter adds no resistance, and the voltmeter draws no current. The battery has no internal resistance. Bars on the right are a drawing scale so the default values sit on the track. The numbers are the true values. Bead speed stands for current. Bead spacing on a path stays even, which is the picture of a steady current. In parallel, each path keeps its own beads, and the shared wires show both sets.

Ranges on this board: V from 3 V to 24 V in steps of 3 V when using the buttons, R from 5 Ω to 40 Ω. Dragging a resistor or the battery moves the value continuously inside those limits. Drag up to raise the value.

## What it shows (craft)
One WebGL scene, void `#140818`, pearl / warm `#ffb36b` / lilac `#b9a2ff`. A board in the dark: a battery, two clear resistor blocks with a warm core (R₁) and a lilac core (R₂), wire paths, an ammeter in the bottom of the loop, and a lilac voltmeter with leads. Dragging empty space leans the view, and the view eases back with a little weight. Solids use MeshStandardMaterial. The resistor blocks thicken slightly as R increases.

## Controls
- Drag a resistor up or down to change its resistance. Drag the battery up or down to change V. A small click selects that resistor for Double R and Halve R.
- Click the voltmeter to move its leads (battery, then R₁, then R₂). Click the ammeter and the board tells you it reads the total current and stays in the loop.
- Chips and the lesson drive the same actions. ← → moves lesson steps.
- `?still` or reduced motion holds a readable still (beads drawn and stopped, meters at the live values). Dragging still updates the picture. `?embed` hides the chrome. `?nolesson` starts with the lesson collapsed.

## Constraints
- One `WebGLRenderer`, `setPixelRatio(Math.min(devicePixelRatio, 1.5))`.
- Local three r170 via `./vendor/three/build/three.module.js`.
- HemisphereLight plus one warm PointLight. No shadow maps. Solids use MeshStandardMaterial.
- RAF pauses on `document.hidden`. Teardown on `pagehide` (`window.__dcCircuitsTeardown`).
- Test hook: `window.__dcCircuits.act(...)`, `.goStep(i)`, `.snapshot()`.

## Physics Lab
Lab home: [`index.html`](index.html). Siblings on this repo’s main line: [`newton-laws-sketch.html`](newton-laws-sketch.html), [`spring-orbit-sketch.html`](spring-orbit-sketch.html).
