# BUILD BRIEF — Honors Biology 3D Models

## Context
`bio-3d-models.html` is a working, self-contained Three.js harness with **Model 1 complete**.
Your job is to add **Models 2–5** following the existing pattern exactly, then wire a launcher
button into `honors-biology-mastery.html`.

Do not redesign the harness. Do not restructure Model 1. Do not touch the question banks.

## Constraints
See `CLAUDE.md` — it is loaded automatically every session and survives compaction.
Do not restate or relax anything in it.

## Pattern to follow
```js
MODELS.push({
  id:'...', name:'N · Title', level:'Levels X–Y · STEELS code',
  hint:'one line shown bottom-left', radius: <camera distance>,
  build:function(ctx){ /* populate ctx.group; ctx.add(mesh,{tag,title,body}) for clickables */ },
  tick:function(t){ /* optional per-frame animation */ }
});
```
Every clickable structure needs a `{tag, title, body}` where `body` is 1–3 sentences of real
explanation written in the same voice as Model 1 — explain the mechanism, don't just name the part.

---

## Model 2 · Membrane Transport — Levels 6 · 3.1.9-12.B
A phospholipid bilayer cross-section (two rows of head-sphere + two tail-rods each).
Floating molecules that the student can watch cross or fail to cross:
- **O₂ / CO₂** (small, nonpolar) — pass straight through the tails.
- **Na⁺ / K⁺** (ionic) — bounce off the hydrophobic core unless they enter a channel protein.
- **Glucose** — passes only through a facilitated-diffusion carrier.
- **Sodium–potassium pump** — animate 3 Na⁺ out / 2 K⁺ in, with a visible ATP → ADP marker.
Include a toggle (a `sendPrompt`-free plain button appended to `#bar`) switching between
"down the gradient" and "against the gradient" so the ATP cost is visible only in the second.
Clickables: bilayer, channel protein, carrier protein, pump, cholesterol.

## Model 3 · DNA to Protein — Levels 14–15 · 3.1.9-12.A
Three linked scenes on one timeline, advanced by a step button:
1. **Double helix** — two antiparallel backbones (helical rung placement), color-coded A/T (2 rungs)
   and C/G (3 rungs). Clicking a base pair explains the hydrogen-bond count.
2. **Transcription** — helix unzips, mRNA strand builds along the template, U replaces T.
3. **Translation** — mRNA threads through a two-subunit ribosome; tRNAs dock by anticodon and
   a polypeptide chain grows. Stop codon releases it.
This is the highest-value model in the set. Spend the most effort here.

## Model 4 · Enzyme & Inhibitor — Level 7 · 3.2.9-12.E
An enzyme with a shaped active site (use a lathe or boolean-free notched geometry).
- Correct substrate docks, induced fit closes slightly, products release, enzyme resets.
- A **competitive inhibitor** docks in the same site and blocks it.
- A **noncompetitive inhibitor** binds elsewhere and visibly deforms the active site.
- A temperature slider that, past the optimum, **denatures** the enzyme — unfold the shape
  and show the substrate no longer fitting.
Tie the info text explicitly to penicillin and beta-lactamase.

## Model 5 · Mitosis & Meiosis — Levels 17–18 · 3.1.9-12.D / .Q
Side-by-side or toggled. Four chromosomes (two homologous pairs, maternal/paternal colored).
Step through the phases with spindle fibers drawn as lines to poles.
- Mitosis: sister chromatids separate → two identical diploid cells.
- Meiosis: crossing over visibly swaps colored segments in prophase I; homologs separate in I,
  sisters in II → four distinct haploid cells.
The payoff is showing **why meiosis I is the reduction division**. Make that unmistakable.

---

## Integration (do last, ~3 turns)
In `honors-biology-mastery.html`, add a "3D Models" link in the footer (`#note`) next to
Export/Import that opens `bio-3d-models.html` in a new tab. Keep the two files separate —
do not inline the 3D code into the main app.

## Validation before you call it done
- Open each model, rotate, zoom, click every labeled part.
- Resize to 380px wide; confirm nothing overflows and touch drag works.
- Check the browser console is clean.
- Confirm `honors-biology-mastery.html` still loads all 40 levels and export/import still works.

## Usage discipline
- One model per exchange. Verify it works before moving on.
- Never paste full file contents into the conversation.
- After Model 3, stop and check Settings → Usage before continuing.
