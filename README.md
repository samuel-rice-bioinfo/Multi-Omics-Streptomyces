# Multi-Omics-Streptomyces
Combining metabolomic and transcriptomic data for a multi-omics approach to understanding Streptomyces strain interactions.
# Natures Crop Protection: A Multi-Omics Approach to Understanding Streptomyces Strain Interactions in Potato Scabies

Author: Samuel Rice

Supervisor: Dr. Francesco Del Carratore

Date: 29/04/2025

##  Overview

This project utilised multi-omics to integrate metabolomics and transcriptomics data, characterising molecular changes during the interactions of four Streptomyces strains (A, B, C, D) grown on interaction plates . The goal was to identify candidate genes, metabolites, and biological pathways potentially underlying strain interactions.

A combination of high-throughput untargeted metabolomics (LC-MS/MS) and RNA-seq was used to generate the data, with the pipeline involving pre-processing, annotation, and integrative analysis, using both R and Python workflows.



## Pipeline Overview

![image](https://github.com/user-attachments/assets/dcf7a011-62e4-4aef-8f5b-cbb9ab4b4dbb)
Figure 1. Multi-omics pipeline. a) Normalisation, annotation and differential analysis of transcriptomic and metabolomic data. b) Multi-omics integration using block scores to predict the response variable.



## Experimental Design
Organisms: Four distinct Streptomyces strains.
Setup: Interaction plates where strains were cultured in proximity to induce molecular responses.
![image](https://github.com/user-attachments/assets/9e8d564f-b78f-440d-a13d-f4d3581d9fa2)



## Data Types:

Metabolomics: Positive and negative mode LC-MS/MS datasets.

Transcriptomics: RNA-Seq datasets, one per strain.

Aim: Identify differential features and pathways linked to antibacterial activity by combining omics layers.

The experimental metadata, feature information, and sample descriptions are fully incorporated into the analysis pipelines.

## Data Description

### Metabolomics Data
#### Two datasets:

metabolomics_pos.RData (positive mode)

metabolomics_neg.RData (negative mode)

#### Contents:

data_pos / data_neg: Mass spectrometry feature matrices (features × samples).

features_info: Feature metadata (m/z values, retention times).

samples_info: Sample metadata (strain identity, batch, day).

### Transcriptomics Data
#### Four datasets:

transcriptomics_strainA.RData, transcriptomics_strainB.RData, transcriptomics_strainC.RData, transcriptomics_strainD.RData

#### Contents:

counts: Raw gene count matrices (genes × samples).

genes_info: Gene metadata (locus tags, gene products).

samples_info: Sample metadata (strain, replicate, timepoint).

### Repository Structure
Metabolomics_positive_pipeline.qmd: Preprocessing and quality control pipeline for positive-mode metabolomics data.

Metabolomics_negative_pipeline.qmd: Preprocessing and quality control pipeline for negative-mode metabolomics data.

Annotations_metabolomics.qmd: Metabolite annotation and integration of feature information post-processing.

transcriptomics_strain_A_pipeline.qmd: Preprocessing and quality control pipeline for strain A transcriptomics data.

PathIntegrate_Analysis.ipynb: Multi-omics data integration analysis using PathIntegrate, including pathway enrichment and molecular candidate identification.

ipaPy2_annotation code.ipynb: Code for running pathway analysis and annotation using the ipaPy2 Python package.

### Tools and Dependencies
##### R (≥ 4.2.0)
tidyverse

limma

edgeR

pheatmap

ComplexHeatmap

MetaboAnalystR

##### Python (≥ 3.9)
pandas

numpy

scipy

pathintegrate

ipapy2

### How to Use
Preprocess the metabolomics and transcriptomics datasets (.qmd files).

Feature annotation with ipaPy2 (Annotations_metabolomics.qmd).

Annotate proteins with DIAMOND

Normalisation (DESEQ2 and PQN)

Differential analysis with Likelihood ratio test (LRT)

Pathway-based integration analysis (PathIntegrate_Analysis.ipynb).

Each code file is independent and can be executed independently following the order above.

### Key Outcomes
Identification of differential metabolites and genes between interacting strains.

Multi-omics integration to uncover biological pathways

Development of a reproducible workflow for future multi-omics integration studies (transcriptomics and metabolomics)

### Acknowledgements
This work was conducted as part of the MSc Bioinformatics research project at The University of Liverpool.
Supervised by Dr. Francesco Del Carratore.
