# Accuracy Assessment of Land Use and Land Cover Classification: A Case Study in the São Luís Intermediate Region with MapBiomas

This repository contains the source code and procedures used in the article: **"Avaliação da Acurácia na Classificação de Uso e Cobertura da Terra: Um Estudo de Caso na Região Intermediária de São Luís com o MapBiomas"**.

The study provides a localized accuracy assessment of [MapBiomas](https://brasil.mapbiomas.org/) data, building upon the original source code developed for the Collection 8 accuracy analysis. This repository is a fork of the original project, specifically adapted for the São Luís intermediate region.

* **Original Repository:** [MapBiomas Accuracy - Collection 8](https://github.com/mapbiomas-brazil/accuraccy/tree/mapbiomas80)
* **Full Article:** [Read it here (DOI: 10.33360/geonordeste.v36i.21680)](https://doi.org/10.33360/geonordeste.v36i.21680)

## Authors

* **Thomas Victor de Sousa Malheiros Rocha**
    * M.Sc. in Environmental Science and Technology
    * Federal University of Maranhão (UFMA)
    * *thomasvictor990@gmail.com*

* **Sérgio Souza Costa**
    * Ph.D. in Applied Computing
    * Associate Professor at the Federal University of Maranhão (UFMA)
    * *sergio.costa@ufma.br*

* **Luís Fernando Cirqueira da Silva Correia**
    * M.Sc. in Environmental Science and Technology
    * Federal University of Tocantins (UFT)
    * *luis.correia@discente.ufma.br*

* **Denilson da Silva Bezerra**
    * Ph.D. in Earth System Science
    * Assistant Professor at the Federal University of Maranhão (UFMA)
    * *denilson.bezerra@ufma.br*

## Repository structure

| Path | Description |
|------|-------------|
| `1_export_gee_input.js` | Google Earth Engine script that exports the accuracy sample points (already exported to `dados/`; not needed to reproduce the analysis). |
| `2_acuracia_sa23z.ipynb` | **Main analysis** — accuracy assessment for chart SA-23-Z (São Luís intermediate region). Produces the results reported in the article. |
| `dados/` | Input data: MapBiomas Collection 8 accuracy samples (2022), strata and class configuration. |
| `exploratorio/check_acuracia_brasil.ipynb` | Exploratory check for the whole of Brazil. **Not part of the article's results**; see the note at the top of the notebook. |
| `tmp/` | Intermediate outputs (HTML tables, shapefiles). Created automatically and ignored by git. |

## Getting Started

The analysis was verified to reproduce with **Python 3.12** (see `.python-version`). The pinned dependencies do not install on Python 3.13.

### 1. Clone the repository

```bash
git clone https://github.com/LambdaGeo/acuracia-slz.git
cd acuracia-slz
```

### 2. Create a virtual environment

It is highly recommended to use a virtual environment to isolate project dependencies.

```bash
python3.12 -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the notebook

The main analysis is performed in a Jupyter Notebook. With the virtual environment active:

```bash
jupyter notebook 2_acuracia_sa23z.ipynb
```

To run it non-interactively from top to bottom:

```bash
jupyter nbconvert --to notebook --execute --inplace 2_acuracia_sa23z.ipynb
```

## How to cite

If you use this code or data, please cite the article (DOI: [10.33360/geonordeste.v36i.21680](https://doi.org/10.33360/geonordeste.v36i.21680)). Citation metadata for the software is available in [`CITATION.cff`](CITATION.cff).
