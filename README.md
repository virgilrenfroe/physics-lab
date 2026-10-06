# Physics Lab

Classroom WebGL exhibits for teaching mechanics (HS / intro college). Soft Noctuary craft, live numbers, guided lesson panels.

## Open

```bash
cd /workspace/physics-lab
python3 -m http.server 8770
```

- Lab index: http://127.0.0.1:8770/
- Hooke’s law & orbits: http://127.0.0.1:8770/spring-orbit-sketch.html
- Newton’s laws: http://127.0.0.1:8770/newton-laws-sketch.html
- Electrostatics: http://127.0.0.1:8770/electrostatics-sketch.html

Query flags: `?embed` · `?still` · `?nolesson`.

## Files

| Path | Role |
|------|------|
| `index.html` | Lab home · cards |
| `spring-orbit-sketch.html` + `-NOTES.md` | Demo 01 |
| `newton-laws-sketch.html` + `-NOTES.md` | Demo 02 |
| `electrostatics-sketch.html` + `-NOTES.md` | Demo 07 · Coulomb field and potential |
| `vendor/three/` | three r170 (local) |

Separate from noctuary-corridor / NestLight / OneShop / BarPal / Harbor / flow-atelier.
