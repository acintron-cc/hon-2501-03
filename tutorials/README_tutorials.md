# Tool tutorials (Algorithmic Fairness, Session 1)

Self-paced Quarto revealjs tutorials, one step per slide, for HON-2501-3. Published address after GitHub Pages is on:
`https://acintron-cc.github.io/hon-2501-03/tutorials/index.html`

## Files

| File or folder | What it is |
|---|---|
| `index.qmd` / `index.html` | Landing page linking to the four tutorials and the datasets folder. |
| `codap-warmup.qmd` / `.html` | CODAP warm-up on compas_classroom.csv, `c_charge_degree` (7 steps). |
| `excel-warmup.qmd` / `.html` | Excel warm-up on the same file (9 steps, Mac with Windows differences). |
| `codap-grouping.qmd` / `.html` | CODAP grouped table: Part A base rates (text only, image slots commented out in the .qmd), Part B confusion-matrix counts (9 steps with stills). |
| `colab-first-run.qmd` / `.html` | First run of `notebooks/fairness_lesson.ipynb` in Colab (8 steps, Gemini, debugging). |
| `styles.scss` | Shared slide theme (colours checked at 4.5:1 or better). |
| `*_files/` | Support files Quarto made for each HTML page (reveal.js, fonts, CSS). **Needed online; keep next to the HTML.** |
| `media/codap/`, `media/excel/`, `media/codap-grouping/`, `media/colab/` | Screenshots, the optional silent MP4s and their README (steps as text, alt text). |
| `README_tutorials.md` | This file. |

To edit: change a `.qmd`, then run `quarto render <file>.qmd` in this folder (Quarto 1.4 or later). Do not add `embed-resources: true`: it would embed the MP4s and make the pages huge.

Part A image slots in `codap-grouping.qmd`: look for lines starting `<!-- ![](media/codap-grouping/`. Save the screenshot under that file name in `media/codap-grouping/`, remove the `<!--` and `-->`, check the alt text, and re-render.

## Publishing

1. Copy the whole `tutorials/` folder (including `media/` and every `*_files/` folder) into the root of the local repo, next to `datasets/` and `notebooks/`.
2. Add an empty file named `.nojekyll` at the **repo root** (it tells GitHub Pages to serve the files exactly as they are).
3. `git add tutorials .nojekyll`, commit, push.
4. On GitHub: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `/ (root)` → Save.** After a minute or two the tutorials are at
   `https://acintron-cc.github.io/hon-2501-03/tutorials/index.html`.
5. Put that link in Blackboard and in the handout.

**Pages serves the whole repo publicly.** Never copy instructor-only files (`instructor/` keys such as metrics_key.csv and weights_key.csv, answer keys, teaching guide) into the repo.
