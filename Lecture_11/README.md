# Single-Cell & Spatial Transcriptomics Analysis in NSCLC

Data science class project analyzing single-cell RNA-seq and spatial transcriptomics data from non-small cell lung cancer (NSCLC) samples.

## Overview

This repository demonstrates the application of data science techniques to transcriptomics data:
- **Dimensionality reduction**: PCA, UMAP, tSNE
- **Unsupervised learning**: Graph-based clustering (Louvain algorithm)
- **Spatial analysis**: Moran's I for spatial autocorrelation

## Data

- **Single-cell RNA-seq**: P1_T1 sample (10X Chromium, 1,436 cells)
- **Spatial transcriptomics**: P10_T1_LUAD sample (10X Visium)

## Notebooks

1. **`01_sc_preprocess_nsclc.ipynb`**: Single-cell preprocessing workflow
   - QC, normalization, feature selection
   - PCA, clustering, UMAP/tSNE visualization

2. **`02_sc_annotation_nsclc.ipynb`**: Cell type annotation
   - Marker-based identification of immune and stromal cell types
   - Manual cluster annotation

3. **`spatial_nsclc.ipynb`**: Spatial transcriptomics analysis
   - Spatial preprocessing with SCTransform
   - Moran's I analysis for spatially variable features
   - Weight matrix visualization

## Key Methods

- **Preprocessing**: Seurat standard workflow, SCTransform for spatial data
- **Clustering**: kNN graph construction + Louvain community detection
- **Cell types identified**: T cells, NK cells, macrophages (M1/M2), monocytes, B cells, dendritic cells, mast cells
- **Spatial analysis**: Binary weight matrix based on spatial adjacency, Moran's I statistics

## Requirements

- R 4.x
- Seurat
- tidyverse
- pheatmap, ggraph, igraph

## Repository Structure

```
.
├── code/                          # Analysis notebooks
├── data/
│   ├── singlecell/
│   │   ├── raw_counts/           # Raw 10X data
│   │   └── processed_counts/     # Processed Seurat objects
│   └── spatial/
│       ├── raw_counts/           # Visium h5 files
│       └── results/              # Moran's I results
└── README.md
```

## Notes

Educational materials prepared for data science students with focus on DS techniques rather than biological interpretation.
