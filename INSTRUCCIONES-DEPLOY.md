# Cómo subir esto a tu GitHub del Tec

Todo el paquete ya viene con tu usuario (`pepeglz-tec`) incrustado en los badges y las URLs. Solo hay que crear el repo, `git init` y push.

**Tiempo estimado:** 5–10 minutos si ya tienes git configurado; +5 min si necesitas instalar/autenticar.

---

## Paso 1 — Crear el repo vacío en GitHub

1. Ve a **https://github.com/new** (asegúrate de estar logueado con la cuenta del Tec, `pepeglz-tec`).
2. **Repository name:** `bt2026-fermentor-simulator` (importante que sea exactamente este nombre — es el que apuntan los badges y las URLs de Colab. Si lo cambias, tendrás que actualizar a mano los READMEs).
3. **Description:** `Aerobic fermentor simulator + kLa dynamic-method fit, designed for BT2026 (Tecnológico de Monterrey). Bilingual (EN/ES).`
4. **Visibilidad:** Public.
5. **NO marques** "Add a README file", "Add .gitignore", ni "Choose a license" — ya vienen en el paquete.
6. Click **Create repository**.

GitHub te va a mostrar una página con las instrucciones de `git remote add`, etc. La puedes ignorar — usa las de abajo, ya están armadas con tu usuario.

---

## Paso 2 — Inicializar git y hacer push

Desde la terminal, dentro de la carpeta `bt2026-fermentor-simulator/`:

```bash
git init
git add .
git commit -m "Initial commit: bilingual simulator + synthetic datasets"
git branch -M main
git remote add origin https://github.com/pepeglz-tec/bt2026-fermentor-simulator.git
git push -u origin main
```

Si es la primera vez que haces push desde esta máquina, GitHub te va a pedir credenciales — usa un **personal access token** (Settings → Developer settings → Personal access tokens → Fine-grained tokens), no tu contraseña de la cuenta. GitHub ya no acepta password auth para git operations desde hace tiempo.

---

## Paso 3 — Verificar

1. Refresca la página de tu repo en GitHub. Deberías ver los archivos.
2. Abre el `README.md` en GitHub y da click en el badge "**Open EN in Colab**". Colab debe cargarte el notebook desde tu repo. Prueba también el "**Open ES in Colab**".
3. En Colab, `Runtime → Run all` y verifica que la app Gradio arranca y emite el URL público. La primera corrida tarda ~30–60 segundos.

Si los badges funcionan y la app levanta, todo está bien.

---

## Paso 4 (opcional pero recomendado) — Zenodo para DOI

Un DOI convierte este repo en un output académico citable — útil para tu evidencia de permanencia M50 y clasificación titular. Cinco minutos de setup, y a partir de ahí cada release nuevo genera DOI automático.

1. Ve a **https://zenodo.org** y logueate con tu cuenta de GitHub (`pepeglz-tec`).
2. En Zenodo, **Settings → GitHub**, y activa el toggle del repo `bt2026-fermentor-simulator`.
3. En GitHub, ve a tu repo → **Releases** → **Create a new release**.
4. **Tag:** `v1.0.0` · **Title:** `BT2026 Fermentor Simulator v1.0.0` · **Description:** un párrafo breve (algo como: *First public release. Includes the Gradio app in EN and ES plus 8 synthetic datasets. Designed as an audit target for the AI-integrated activity in the course.*).
5. **Publish release.**
6. En 1–2 minutos, Zenodo detecta el release y te da un DOI automáticamente. Aparece un badge (algo como `DOI 10.5281/zenodo.XXXXXXX`) que puedes pegar arriba en el README.

---

## Cambios futuros

Después del primer push, cualquier cambio se sube así:

```bash
# Editar archivos localmente
git add archivo-que-cambió.ext
git commit -m "descripción breve del cambio"
git push
```

Cuando quieras cortar un nuevo release (para que Zenodo emita nuevo DOI):
- **GitHub → Releases → Draft a new release**.
- Tag: `v1.1.0` (o el incremento que aplique) y publish.

---

## Qué NO subir aquí

Cerciórate de que estos archivos **nunca** entren al repo público:
- Manual del implementador (contiene el marco pedagógico completo con los 5 modos IA).
- Anexo docente v4 (contiene la tabla explícita de aristas por dataset y los 8 supuestos).
- Quiz con respuestas + rúbrica.
- La plantilla Canva de la infografía integradora (es tuya y del Tec, no material open).

Estos se distribuyen por Canvas o por Drive institucional, no por GitHub.

El `.gitignore` incluido ya bloquea las carpetas `private/`, `notes/` y `scratch/` por si tienes archivos locales que no quieres versionar por accidente — si los quieres a la mano en tu working directory, ponlos en alguna de esas.
