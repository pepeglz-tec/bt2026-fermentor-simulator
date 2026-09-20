# BT2026 · Aerobic Fermentor Simulator

[![Open EN in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pepeglz-tec/bt2026-fermentor-simulator/blob/main/notebooks/bt2026-fermentor-simulator-EN.ipynb) &nbsp; [![Open ES in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pepeglz-tec/bt2026-fermentor-simulator/blob/main/notebooks/simulador-fermentador-BT2026-ES.ipynb) &nbsp; [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22850011.svg)](https://doi.org/10.5281/zenodo.22850011)

> 🇪🇸 **En español:** [README.es.md](README.es.md)

A didactic Gradio web app to determine **k<sub>L</sub>·a** by the dynamic method and to simulate a full aerobic fermentation. Designed for the course **BT2026 — Transport Phenomena Analysis** at Tecnológico de Monterrey.

The simulator is **also an audit target**: it makes several assumptions it does not declare in its interface. The pedagogical activity asks students to find them by reading the code with AI assistance and contrasting the model against their assigned experimental dataset.

---

## What's in this repo

| Path | What it is |
|---|---|
| `notebooks/bt2026-fermentor-simulator-EN.ipynb` | Colab notebook (English) — Gradio app with 3 tabs. |
| `notebooks/simulador-fermentador-BT2026-ES.ipynb` | Colab notebook (Spanish) — same app in Spanish. |
| `datasets/set-{1..5}-equipo-{a..e}.csv` | Five synthetic team datasets. Each has a different "edge" (a physical/experimental condition that violates one of the simulator's implicit assumptions). |
| `datasets/quiz-{a,b,c}-*.csv` | Three additional datasets used in the individual quiz. |

The teaching materials themselves (implementer manual, teacher annex, quiz answer key, rubric) are **intentionally not published here** — they are distributed privately through institutional channels so students cannot short-circuit the auditing exercise by finding the answers.

---

## Quick start

The fastest path — click the badge above to open one of the notebooks in Colab, then hit `Runtime → Run all`. A public Gradio URL (`https://xxxx.gradio.live`) will appear at the bottom of the last cell; open it in a new tab and you have the app.

To use a dataset:

1. In the app, go to **Tab 1 (kLa determination)**.
2. Upload one of the CSVs from `datasets/`.
3. Click **Fit k_L·a**.

For the full auditing task, read Tab 3 inside the app.

---

## Data dictionary

Every CSV has two columns, no header row required (the app reads by position):

| Column | Meaning | Units |
|---|---|---|
| 1 | Time from the start of the dynamic method | seconds |
| 2 | Dissolved oxygen concentration measured by the sensor | mg/L |

The datasets are **synthetic** but were generated using physically-motivated equations plus deliberate perturbations. Details of the perturbations are part of the teaching materials and not disclosed here.

---

## Requirements

The notebooks are designed for Google Colab, which comes with all needed libraries preinstalled except a Gradio upgrade. If you want to run them locally in a Jupyter kernel:

```bash
pip install numpy pandas scipy matplotlib gradio
```

The Gradio public URL (`--share`) works out of the box on Colab. On a local Jupyter, the URL will be limited to `localhost` unless you configure `share=True` and have a valid ngrok-like tunnel.

---

## Pedagogical framework

This simulator is one component of a larger AI-integrated learning activity. Its role in the activity is deliberately dual:

- As a **computational tool**, it lets students obtain k<sub>L</sub>·a numbers and simulate fermentations.
- As an **audit object**, it embodies the epistemological point that AI-assisted computation is never assumption-free. Students learn to read code, question its silent choices, and validate against experimental reality.

The full pedagogical rationale — including the "five AI moments" framework it exercises — is documented in the private teacher materials.

---

## License

MIT — see [LICENSE](LICENSE). You are free to fork, adapt, and redistribute the code with attribution.

## How to cite

If you use this simulator in your own teaching, please cite it as:

González-Valdez, J. (2026). *An Auditable Aerobic Fermentor Simulator Tool for kₗa Determination and AI-Integrated Transport Phenomena Education* (Version v1.0.0) [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.22850011

BibTeX:

```bibtex
@software{gonzalezvaldez_2026_fermentor,
  author       = {González-Valdez, José},
  title        = {An Auditable Aerobic Fermentor Simulator Tool
                  for k\_L a Determination and AI-Integrated
                  Transport Phenomena Education},
  month        = sep,
  year         = 2026,
  publisher    = {Zenodo},
  version      = {v1.0.0},
  doi          = {10.5281/zenodo.22850011},
  url          = {https://doi.org/10.5281/zenodo.22850011}
}
```

---

## Contact

Course design and simulator: José González-Valdez · School of Engineering and Sciences · Tecnológico de Monterrey.
