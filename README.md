# Prueba Práctica — Unidad IV — Paralelo B

**Asignatura:** Ingeniería de Requisitos (ISR-401)
**Universidad Técnica Estatal de Quevedo** — Facultad de Ciencias de la Ingeniería, Carrera de Ingeniería de Software
**Caso:** Sistema de Reserva de Citas Médicas
**Estudiante:** Yeranick Muñoz — 4to "B"
**Docente:** Ing. Gleiston Guerrero, Mg.

**Repositorio:** https://github.com/ymunozq/PRUEBA_PR-CTICA_U4_MU-OZ_B.git

---

## Compilación

- **Compilador:** `pdflatex`
- **Archivo principal:** `main.tex` (es el único `.tex` que se compila)

### Orden de comandos

Ejecutar los cuatro comandos en este orden exacto, desde la raíz del repositorio:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

La primera pasada de `pdflatex` genera el archivo `main.aux` con las claves citadas; `bibtex` las resuelve contra `referencias.bib` y produce `main.bbl`; la segunda pasada incorpora la bibliografía y la tercera fija la numeración definitiva de citas y referencias cruzadas.

El documento usa `natbib` con `\bibliographystyle{plainnat}` y `\bibliography{referencias}`. El PDF resultante tiene **9 páginas**.

## Dependencias

Paquetes LaTeX utilizados en el preámbulo de `main.tex`:

| Paquete | Opciones |
|---|---|
| `inputenc` | `utf8` |
| `fontenc` | `T1` |
| `helvet` | `scaled=0.92` |
| `textcomp` | — |
| `geometry` | `a4paper`, márgenes personalizados, `headheight=15pt` |
| `amsmath`, `amssymb` | — |
| `graphicx` | — |
| `xcolor` | `table`, `dvipsnames` |
| `array` | — |
| `tabularx` | — |
| `multirow` | — |
| `colortbl` | — |
| `booktabs` | — |
| `enumitem` | — |
| `microtype` | `protrusion=true`, `expansion=false` |
| `parskip` | — |
| `titlesec` | — |
| `fancyhdr` | — |
| `caption` | — |
| `pdflscape` | — |
| `natbib` | `numbers`, `sort&compress` |
| `hyperref` | `colorlinks=true` y colores institucionales |
| `tcolorbox` | `most` |
| `tikz` | librerías: `shapes.geometric`, `shapes.multipart`, `arrows.meta`, `positioning`, `calc`, `fit`, `backgrounds` |

Clase del documento: `article` con opciones `11pt`, `a4paper`, `oneside`.

### Instalación en Debian/Ubuntu

```bash
sudo apt install texlive-latex-base texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended texlive-pictures texlive-bibtex-extra
```

### Instalación en Windows (MiKTeX / TeX Live)

Instalar [MiKTeX](https://miktex.org/download) o [TeX Live](https://www.tug.org/texlive/) y ejecutar los mismos cuatro comandos desde una terminal (o desde TeXworks / TeXstudio seleccionando `pdflatex` y `bibtex`).

En **MiKTeX**, la opción *"Install missing packages on-the-fly"* (activada por defecto) descarga automáticamente cualquiera de los paquetes anteriores que falte durante la primera compilación. En **TeX Live**, una instalación completa (`scheme-full`) ya los incluye todos.

## Estructura de carpetas

```
PRUEBA_PR-CTICA_U4_MU-OZ_B/
├── main.tex          <- archivo principal, el único .tex que se compila
├── referencias.bib   <- 6 referencias en formato BibTeX
├── main.pdf          <- PDF compilado, versionado en el repositorio
├── README.md
└── .gitignore
```

Los tres diagramas UML del desarrollo (P1 diagrama de clases, P2 diagrama de actividades y P3 máquina de estados) están construidos en TikZ dentro del propio `main.tex`, por lo que no existe una carpeta de figuras ni se requieren imágenes externas.

Los archivos auxiliares que genera LaTeX (`.aux`, `.log`, `.out`, `.toc`, `.bbl`, `.blg`, `.fls`, `.fdb_latexmk`, `.synctex.gz`) están excluidos mediante `.gitignore`. El archivo `main.pdf` **sí** se versiona, porque el enunciado lo exige como entregable.
