# RNA-Seq Analysis Pipeline using GEO: GSE295712

This repository contains an end-to-end RNA-seq analysis pipeline using publicly available data from [GEO: GSE295712](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE295712). The dataset compares transcriptomic profiles between lung tissue and lymphatic tissue in a preclinical cancer model.

## 📂 Dataset

- **GEO Accession**: GSE295712
- **Data type**: Gene-level count data (`featureCounts`)
- **Samples**:
  - Lung: 2 replicates
  - Lymph: 3 replicates

---

## 📦 Tools and Packages

All analyses were conducted in **R (v 4.5)** using the following packages:

- `DESeq2`
- `ggplot2`
- `dplyr`, `tidyverse`
---

## 🔬 Analysis Workflow

### 1. Data Preprocessing

- Downloaded `GSE295712_gene-featureCount-else-int_name.txt.gz` from GEO.
- Filtered and formatted count matrix.
- Removed duplicates and set `GeneName` as rownames.

### 2. Differential Expression Analysis (DESeq2)

- Compared gene expression between Lung and Lymph groups.
- Applied filtering for low-count genes.
- Extracted differentially expressed genes (DEGs) using `DESeq2`.

#### Output:
- `kras_df.tsv` — full DE results

### 4. Gene Set Enrichment Analysis (GSEA)

- Ranked genes by DESeq2 statistic
- Generated bar plots of up/downregulated pathways

#### Output:

- `rnk.csv` - pre-ranked file for GSEA

### 3. Visualization

- Scatterplot of top 50 DE genes & Angiogenesis hallmark pathway for VEGFA specific information

---

## 📁 Project Structure


GSE295712_RNAseq_Analysis

├── data/ # Raw and processed input files

│ └── GSE295712_featureCounts.txt

├── results/ # Output tables

│ ├── kras_df.tsv

│
├── scripts / RNA-Seq.Rmd

│ ├── 01_preprocess

│ ├── 02_deseq2_analysis

│ ├── 03_gsea

│ └── 04_visualizations

│
└── README.md


---

## 📌 Notes

- Gene names were aggregated if duplicated using `aggregate()`.
- GSEA was performed using Hallmark gene sets (`msigdbr`).

---

## 🧬 Author

**Shirsa Udgata**  
Cancer Biologist  
📍 Madison, WI  
www.linkedin.com/in/shirsa-udgata 

---














