# DNA Methylation Comparison: Epigenica vs Illumina EPIC Array

This repository contains R and Bash scripts used to compare two DNA methylation technologies:

- **Epigenica EpiFinder GenomePro**
- **Illumina MethylationEPIC Array**

## Dataset

The analysis is based on samples from **four healthy blood donors**.

## Data Processing

### EpiFinder Data
- Pre-processing performed using the **MIUNTE pipeline**
- Additional processing with **DeepTools** (via Conda)
- Output generated as **BigWig files**, used for downstream analysis

### Illumina EPIC Array Data
- Data obtained from the study:  
  *"Epigenetic rewiring of pathways related to odour perception in immune cells exposed to SARS-CoV-2 in vivo and in vitro"* (2022)
- Analysis starts from **raw IDAT files**


## Analysis Overview
The workflow integrates sequencing-based and array-based methylation data for comparative analysis. It includes the following components:

### 1. CpG Site Analysis

 #### M-value Analysis (No Normalization or Filtering)
 - Overlayed histograms
 - Spearman correlation
 
 #### M-value Analysis (Quantile Normalization)
 - Overlayed histograms
 - Spearman correlation
 - Bland–Altman plots
 
 #### Beta Value Analysis
 - Calculation of beta values
 
 #### Active Tuberculosis (TB) Analysis
 - Delta beta calculation
 - Principal Component Analysis (PCA)
 - Correlation matrix
 - Boxplots for the top 7 differentially methylated CpG sites (DMCs)

### 2. CpG island analysis
 - Extraction of CpG islands
 - Filtering of CpG islands
 - Normalization of Illumina beta values using Noob
 - Normalization of Epigenica beta values using cyclic loess
 - Overlaying histogram for both MBDs - read counts vs beta values
 - Histogram of read count vs number of CpG islands - Epigenica data only

 #### Beta values comparison
 - Overlaying histograms
 - Confusion matrix

### 3. Age clock probes analysis
 - Extracting significant probes for biological age
 - Confusion matrix
 - GO enrichment analysis for misclassified probes
 - Spearman's correlation
