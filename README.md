# alfredz-tesis

[**Ver / Descargar PDF de la tesis**](https://TU_USUARIO.github.io/alfredz-tesis/main.pdf)  
*(Sustituye `TU_USUARIO` por tu usuario de GitHub. Activa GitHub Pages desde la rama **main** en Settings → Pages.)*

---

## Workflows

- **`build-latex.yml`** — Producción: se ejecuta solo en **push a main** (y en *Run workflow*). Compila el LaTeX y sube el PDF a la rama **release** (`main.pdf` en la raíz + `pdf/main-<sha>.pdf` como historial). No se dispara en PRs.
- **`pr-preview.yml`** — Review de PRs: se ejecuta en cada **pull request hacia main**. Compila el PDF del PR y el de `main`, genera un diff visual (PDF con diferencias en rojo) y comenta en el PR con enlaces para descargar los artifacts (`tesis-pdf`, `base-pdf`, `pdf-diff`).

```
Rama  →  PR  →  [pr-preview: build + diff + comentario]
Merge a main  →  [build-latex: build + push a release]  →  Pages desde release
```
