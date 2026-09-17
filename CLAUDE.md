# Honors Biology — project rules

Two standalone HTML files. No build step, no framework, no package.json.
Everything runs by double-clicking the file.

- `honors-biology-mastery.html` — 40-level question app, 360 items. **Do not edit the
  question banks or level map** unless explicitly asked. Treat it as finished.
- `bio-3d-models.html` — Three.js model viewer. Active work happens here.
- `BUILD-BRIEF.md` — the task spec. Read it before starting work.

## Non-negotiable technical constraints

These have already broken builds once. They apply to every edit, every session.

- **Three.js r128 only**, from `https://cdnjs.cloudflare.com`. No other external host,
  no other version, no npm.
- **`THREE.OrbitControls` does not exist in r128.** A custom orbit controller is already
  implemented in `bio-3d-models.html`. Use it. Never import or reference OrbitControls.
- **`THREE.CapsuleGeometry` does not exist in r128** (added r142). Use the `capsule()`
  helper already defined in the file.
- Safe geometries: Sphere, Cylinder, Torus, TorusKnot, Box, Plane, Ring, Lathe, Tube.
- No `localStorage`, no `fetch`, no network calls of any kind after page load.
- Each file must stay **self-contained** — inline all CSS and JS, no separate assets.

## Conventions

- Add models only by pushing to the `MODELS` array. Follow Model 1 exactly; it is the
  reference implementation.
- Every clickable structure needs `{tag, title, body}`. The `body` explains the mechanism
  in 1–3 sentences — match Model 1's voice. Never just name the part.
- Reuse the existing CSS variables. Do not introduce a new palette.
- Must work on touch: drag to rotate, pinch to zoom. The harness handles this already;
  don't add mouse-only interactions.

## Working style

- Build and verify **one model per exchange**. Do not batch.
- Edit files in place. **Never** print the full contents of either HTML file to the
  terminal — `honors-biology-mastery.html` is 165 KB and doing so wastes the session.
- After each model works, commit: `git add -A && git commit -m "model N: <name>"`.
- Use Sonnet. Do not switch to Fable for this project.
