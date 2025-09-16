# Single-Cell RNA-seq Analysis of CD8+ T Cells

This project provides a comprehensive analysis of a publicly available single-cell RNA sequencing (scRNA-seq) dataset of CD8+ T cells from a healthy donor, provided by 10x Genomics.  
The analysis is conducted using modern computational tools, including Scanpy, Polars, and Matplotlib, to process, analyze, and visualize the data.

---

## 🧬 Dataset

The dataset used in this analysis is the "CD8+ T cells of healthy donor 1" dataset from 10x Genomics. It can be accessed and downloaded from the following link:

[10x Genomics Dataset: CD8+ T cells of healthy donor 1](https://www.10xgenomics.com/datasets/cd-8-plus-t-cells-of-healthy-donor-1-1-standard-3-0-2)

---

## 🔬 Workflow

The analysis pipeline is structured as follows:

1.  **Data Loading and Preprocessing**: The raw gene expression matrix is loaded from the HDF5 file format (`.h5`).

2.  **Quality Control (QC)**:
    * Mitochondrial genes are identified and quantified.
    * QC metrics such as total UMI counts, number of genes per cell, and mitochondrial DNA percentage are calculated.
    * Low-quality cells are filtered out based on gene counts and mitochondrial content to ensure data integrity.

3.  **Normalization and Feature Selection**:
    * The data is normalized to account for differences in sequencing depth between cells.
    * Highly variable genes (HVGs) are identified to focus on biologically significant genes for downstream analysis.

4.  **Dimensionality Reduction**:
    * **Principal Component Analysis (PCA)** is performed on the scaled data to reduce its dimensionality while retaining most of the variance.
    * **Uniform Manifold Approximation and Projection (UMAP)** is used to visualize the data in a 2D space, revealing the underlying cell population structure.

5.  **Clustering and Gene Marker Identification**:
    * The Leiden algorithm is applied to cluster cells into distinct populations based on their gene expression profiles.
    * Marker genes for each cluster are identified and visualized using Heatmap and UMAP.

---

## 🚀 Technologies Used

* **Python 3**
* **Scanpy**: For single-cell analysis.
* **Polars**: For data manipulation and analysis.
* **Matplotlib & Seaborn**: For data visualization.
* **NumPy & Pandas**: For numerical operations and data handling.
* **igraph & leidenalg**: For clustering analysis.

---

## 📊 Results

The analysis identified 23 distinct cell populations from the initial 55,206 cells.  
After quality control, 49,661 cells were analyzed.  
Key findings include the identification of various CD8+ T cell subtypes based on the expression of the following 6 marker genes - GZMB, PRF1, IFNG, TNF, CCR7, and IL7R.  
The final clustered data is visualized using UMAP plots, which clearly delineate the different cell populations.  

