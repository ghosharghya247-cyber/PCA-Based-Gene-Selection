# PCA-Based Gene Selection

A bioinformatics project that applies **Principal Component Analysis (PCA)** to identify the most informative genes from the **GSE6613 microarray dataset** using the GEO (Gene Expression Omnibus) database.

## Overview

This notebook demonstrates a PCA-based approach to gene selection from high-dimensional gene expression data. It loads the GSE6613 dataset (105 samples × 22,283 genes), applies PCA to capture 95% of the variance, and ranks genes by their weighted contribution across the top principal components.

## Workflow

1. **Import Libraries** — NumPy, Pandas, Matplotlib, Seaborn, scikit-learn
2. **Load Dataset** — Downloads and parses the GSE6613 dataset via `GEOparse`
3. **Prepare Feature Matrix** — Transposes the expression matrix and standardizes features using `StandardScaler`
4. **Apply PCA (95% variance)** — Selects 91 components explaining ~95.14% of total variance
5. **Gene Selection via Top 5 PCs** — Ranks genes by weighted PCA loading scores across the top 5 principal components
6. **Gene Selection via Top 10 PCs** — Re-runs gene selection using the top 10 principal components for comparison
7. **Compare Results** — Identifies overlapping and unique genes between the two selection strategies

## Dataset

- **GEO Accession:** GSE6613
- **Platform:** GPL96 (Affymetrix Human Genome U133A Array)
- **Samples:** 105
- **Genes (probes):** 22,283 (21,225 after gene symbol mapping)

## Key Results

| Strategy | Top Gene | Weight Score |
|----------|----------|--------------|
| Top 5 PCs | EIF4A2 /// MIR1248 /// ... | 0.002841 |
| Top 10 PCs | EPHB2 | 0.003390 |

## Requirements

```
numpy
pandas
matplotlib
seaborn
scikit-learn
GEOparse
```

## Usage

Run the notebook `PCA_Gene_Selection.ipynb` in a Jupyter or Google Colab environment. The dataset is automatically downloaded from NCBI GEO on first run.
