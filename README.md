# Universidade de Santiago de Compostela
## Facultade de Física
## Curso Física Nuclear e de Partículas
### autor: J. A. Hernando, X. Cid Vidal
### data : setembro 2026


Este repositorio contén Python-Notebooks e código Python para as clases
de "Introdución á Física de Partículas" da materia introdutoria "Física Nuclear e de Partículas" da Universidade de Santiago de Compostela.

Índice e ligazóns ao material do curso en *indice.ipynb*

Preme aquí para iniciar a túa sesión interactiva (ten paciencia!):

Google: 
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/xabiercidvidal/USC-FNeP/blob/main/notebooks/introduccion.ipynb)

Binder:
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/xabiercidvidal/USC-FNeP/main)


## Contorno

Para **executar os notebooks e compilar o Book** (contorno do autor):

```bash
conda env create -f environment.yml
conda activate fnyp
jupyter-book build .
```

Para que os notebooks se abran con este contorno desde calquera Jupyter, sen depender
de cal estivese activo ao arrincalo, convén rexistrar o kernel unha vez:

```bash
conda activate fnyp
python -m ipykernel install --user --name fnyp --display-name "Python (fnyp)"
```

Aparece entón como **Python (fnyp)** no selector de kernel.

Para **só executar os notebooks** abonda con `requirements.txt`, que é o que usa
Binder:

```bash
pip install -r requirements.txt
```

As versións están acoutadas a propósito nos dous ficheiros, e deben manterse en
paralelo: sen cotas, Binder resolve o último de cada día e as figuras que ve o
alumnado poden non coincidir coas que se compilan en local.

> **jupyter-book está fixado na serie 0.15.** A 2.x é unha reescritura sobre o
> motor MyST e non le este `_config.yml` nin este `_toc.yml`. Actualizar esixe migrar
> os dous ficheiros e as directivas `admonition` dos obradoiros.

## Publicación do Book

A web do curso, <https://xabiercidvidal.github.io/USC-FNeP/>, sérvea GitHub Pages desde
a rama `gh-pages`. **Non hai que tocar esa rama a man**: o fluxo de traballo
`.github/workflows/deploy-book.yml` compila o Book e actualízaa en cada `push` a
`main` que toque os notebooks, `_config.yml`, `_toc.yml`, `intro.md` ou
`environment.yml`. Tamén pode lanzarse a man desde a lapela *Actions*.

O servidor crea o contorno a partir de `environment.yml`, de modo que compila coas
mesmas versións acoutadas que en local e as figuras coinciden.

Se o fluxo falla e cómpre publicar de inmediato, o despregamento manual segue sendo
válido:

```bash
conda activate fnyp
jupyter-book build .
ghp-import -n -p _build/html
```

GitHub Pages tarda uns minutos en servir a versión nova, e a cabeceira de caché é de
dez minutos: para comprobalo, recarga forzando.
