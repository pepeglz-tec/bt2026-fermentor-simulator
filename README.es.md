# BT2026 · Simulador de fermentador aerobio

[![Abrir EN en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pepeglz-tec/bt2026-fermentor-simulator/blob/main/notebooks/bt2026-fermentor-simulator-EN.ipynb) &nbsp; [![Abrir ES en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/pepeglz-tec/bt2026-fermentor-simulator/blob/main/notebooks/simulador-fermentador-BT2026-ES.ipynb) &nbsp; [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22850011.svg)](https://doi.org/10.5281/zenodo.22850011)

> 🇺🇸 **In English:** [README.md](README.md)

App web didáctica en Gradio para determinar **k<sub>L</sub>·a** por el método dinámico y para simular una fermentación aerobia completa. Diseñada para el curso **BT2026 — Análisis de Fenómenos de Transporte** en el Tecnológico de Monterrey.

El simulador es **también un objeto de auditoría**: hace varios supuestos que no declara en su interfaz. La actividad pedagógica pide que estudiantes los encuentren leyendo el código con apoyo de IA y contrastando el modelo contra su dataset experimental asignado.

---

## Qué hay en este repositorio

| Ruta | Qué es |
|---|---|
| `notebooks/bt2026-fermentor-simulator-EN.ipynb` | Notebook de Colab (inglés) — app Gradio con 3 tabs. |
| `notebooks/simulador-fermentador-BT2026-ES.ipynb` | Notebook de Colab (español) — la misma app en español. |
| `datasets/set-{1..5}-equipo-{a..e}.csv` | Cinco datasets sintéticos por equipo. Cada uno tiene una "arista" distinta (una condición físico-experimental que viola uno de los supuestos implícitos del simulador). |
| `datasets/quiz-{a,b,c}-*.csv` | Tres datasets adicionales usados en el quiz individual. |

Los materiales pedagógicos en sí (manual del implementador, anexo docente, clave de respuestas del quiz, rúbrica) **intencionalmente no se publican aquí** — se distribuyen de forma privada por canales institucionales para que estudiantes no puedan cortocircuitar el ejercicio de auditoría encontrando las respuestas.

---

## Arranque rápido

La ruta más rápida — da click al badge de arriba para abrir uno de los notebooks en Colab, y luego `Runtime → Run all`. Al fondo de la última celda aparecerá un URL público de Gradio (`https://xxxx.gradio.live`); ábrelo en pestaña nueva y ya tienes la app.

Para usar un dataset:

1. En la app, ve al **Tab 1 (Determinación de kLa)**.
2. Sube uno de los CSVs de `datasets/`.
3. Da click en **Ajustar k_L·a**.

Para la tarea completa de auditoría, lee el Tab 3 dentro de la app.

---

## Diccionario de datos

Cada CSV tiene dos columnas, sin encabezado necesario (la app lee por posición):

| Columna | Significado | Unidades |
|---|---|---|
| 1 | Tiempo desde el inicio del método dinámico | segundos |
| 2 | Concentración de oxígeno disuelto medida por el sensor | mg/L |

Los datasets son **sintéticos** pero se generaron con ecuaciones físicamente motivadas más perturbaciones deliberadas. El detalle de las perturbaciones es parte del material docente y no se revela aquí.

---

## Requisitos

Los notebooks están diseñados para Google Colab, que trae todas las bibliotecas necesarias preinstaladas excepto una actualización de Gradio. Si quieres correrlos localmente en un kernel de Jupyter:

```bash
pip install numpy pandas scipy matplotlib gradio
```

El URL público de Gradio (`--share`) funciona directo en Colab. En un Jupyter local el URL se limitará a `localhost` a menos que configures `share=True` y tengas un túnel ngrok o similar.

---

## Marco pedagógico

Este simulador es un componente de una actividad de aprendizaje integrada con IA más grande. Su papel en la actividad es deliberadamente dual:

- Como **herramienta computacional**, permite a estudiantes obtener números de k<sub>L</sub>·a y simular fermentaciones.
- Como **objeto de auditoría**, encarna el punto epistemológico de que la computación asistida por IA nunca está libre de supuestos. Estudiantes aprenden a leer código, cuestionar sus decisiones silenciosas, y validar contra la realidad experimental.

La justificación pedagógica completa — incluido el marco de los "cinco momentos de IA" que la actividad ejercita — está documentada en los materiales docentes privados.

---

## Licencia

MIT — ver [LICENSE](LICENSE). Puedes hacer fork, adaptar y redistribuir el código con atribución.

## Cómo citar

Si usas este simulador en tu propia docencia, por favor cítalo así:

González-Valdez, J. (2026). *An Auditable Aerobic Fermentor Simulator Tool for kₗa Determination and AI-Integrated Transport Phenomena Education* (Versión v1.0.0) [Software]. Zenodo. https://doi.org/10.5281/zenodo.22850011

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

## Contacto

Diseño del curso y del simulador: José González-Valdez · Escuela de Ingeniería y Ciencias · Tecnológico de Monterrey.
