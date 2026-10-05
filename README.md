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
- Work & energy: http://127.0.0.1:8770/work-energy-sketch.html

Query flags: `?embed` · `?still` · `?nolesson`.

## Files

| Path | Role |
|------|------|
| `index.html` | Lab home |
| `spring-orbit-sketch.html` + `-NOTES.md` | Demo 01 |
| `newton-laws-sketch.html` + `-NOTES.md` | Demo 02 |
| `work-energy-sketch.html` + `-NOTES.md` | Demo 03 · work–energy theorem |
| `vendor/three/` | three r170 (local) |

Separate from noctuary-corridor / NestLight / OneShop / BarPal / Harbor / flow-atelier.
