
# Apple Quality Analysis — PCA & Hierarchical Clustering

[![Python](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

This repository contains a reproducible, critical exploratory analysis of apple quality measurements. The analysis uses Principal Component Analysis (PCA) and Hierarchical Agglomerative Clustering (HAC) to reveal latent structure in the data and to evaluate the adequacy of the existing binary quality labeling (`good` / `bad`).

The notebook and accompanying scripts focus on transparent, reproducible data processing, visualizations, and cluster-based interpretation to inform better, more objective quality labels.

**Key takeaways**

- The dataset exhibits multidimensional variation in traits such as size, weight, sweetness, crunchiness, juiciness, ripeness and acidity.
- PCA reduces dimensionality while retaining most variance, enabling clearer visualization and interpretation of dominant traits.
- Hierarchical clustering uncovers four coherent groups that do not align cleanly with the original binary labels, which suggests the existing labeling may oversimplify apple quality.
- The analysis provides a data-driven alternative labeling (cluster profiles) and recommendations for improved quality-control procedures. For detailed explanations, visualizations, and step-by-step analysis, refer to the Jupyter notebook.

**Project structure**

- `environment.yaml` — Optional Conda environment specification used to reproduce the analysis environment.
- `requirements.txt` — Python packages required for pip-based setups.
- `dataset/apple_quality.csv` — Core dataset used for all analyses.
- `notebooks/Apple_Quality_Analysis.ipynb` — Main, executable analysis notebook (PCA + CAH) and figures.

**How this repository treats the existing labeling (critical analysis)**

This work is explicitly a critique of the original binary `Quality` label. Key points:

- Exploratory analysis and PCA reveal that apple quality is multidimensional rather than binary. Several clusters span both `good` and `bad` labels.
- Hierarchical clustering produces groups characterized by distinct combinations of ripeness, sweetness, acidity and texture that are not well represented by a single binary label.
- When label overlap with clusters is high, supervised classifiers trained on the original labels are likely to be unstable and may reflect labeling noise rather than true sensory differences.
- The notebook therefore recommends a cluster-informed re-labeling (or multi-class / ordinal labels) and documents cluster profiles (e.g., "Crispy Fresh", "Sour Juicy", "Sweet Premium", "Mature Mild") as interpretable categories.

**Quick start — clone, install, run**

1. Clone this repository (start here):

```powershell
git clone https://github.com/JesserBenNasr/apple-quality-analysis.git
cd apple_quality-analysis
```

2. Create and activate the environment (Conda preferred):

```powershell
conda env create -f environment.yaml
conda activate apple_quality
```

If you prefer pip, create a virtual environment and install requirements:

```powershell
python -m venv .venv
.\\.venv\\Scripts\\Activate.ps1
python -m pip install -r requirements.txt
```

3. Start Jupyter and open the notebook:

```powershell
jupyter notebook
```

Open `notebooks/Apple_Quality_Analysis.ipynb` and run the cells from top to bottom. The notebook is structured in sections: Data → PCA → Clustering → Interpretation.

**Reproducing the key outputs**

- Ensure `dataset/apple_quality.csv` is present and unchanged from the version used for analysis.
- Use the provided environment files to guarantee consistent package versions.
- Figures and tables in the notebook are ready for export; the notebook contains code to save plots if you want standalone PNG/SVG outputs.

**Interpretation guidance**

- Use the cluster profiles and PCA loadings to interpret which features drive each cluster and component.
- When designing quality-control rules, prefer multi-criteria thresholds or cluster membership over a single binary label.
- Consider collecting additional contextual labels (e.g., harvest date, storage conditions) to explain cluster drivers and reduce label noise.

**Contributing**

Contributions are welcome:

- Additions to preprocessing, feature engineering, or alternative clustering approaches.
- Scripts for automated figure export or model training using cluster-based labels.
- Documentation improvements or dataset provenance details.

Please open an issue or a pull request describing your proposed change.

**License**
This project is released under the MIT License.  
You are free to use, modify, and distribute this code with attribution.
