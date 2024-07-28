# UNR_Assessment

# Protein Quantification Analysis

## Overview

This repository contains an analysis of a quantified protein dataset obtained through Data Independent Acquisition (DIA). The goal of this analysis is to explore the dataset, handle missing values, perform statistical tests, and apply clustering techniques to identify patterns and significant proteins. 

## Table of Contents

- Introduction
- Data Acquisition
- Data Exploration
  - Exploratory Feature Corrections
  - Handling Missing Values
  - Data Distribution
- Summary Statistics
- Hypothesis Testing
- Clustering
- Conclusion

## Introduction

The analysis focuses on a dataset containing protein quantification data from DIA experiments. Key objectives include identifying interesting findings through exploratory data analysis, hypothesis testing, and clustering. This comprehensive examination aims to uncover significant patterns, validate biological hypotheses, and potentially identify novel biomarkers or therapeutic targets.

## Data Acquisition

The dataset used for this analysis is a tab-delimited text file containing protein quantification data. The file includes columns such as:
- `PG.ProteinGroups`: Identifiers for protein groups.
- `PG.Genes`: Gene symbols associated with proteins.
- `PG.Organisms`: Organism of origin.
- `EG.IsDecoy`: Indicator for decoy proteins.
- `NrOfPeptide Columns`: Number of peptides used for quantification.
- `ProteinQuant Columns`: Quantified intensity of proteins.

The dataset was loaded using R and initial data inspection was performed.

## Data Exploration

### Exploratory Feature Corrections

- The dataset was cleaned by separating protein groups into individual rows, removing duplicates, and filtering out decoy proteins.
- Aggregated data and identified patterns were checked to ensure data integrity.

### Handling Missing Values

- Missing values were assessed, and imputation strategies were applied using Multiple Imputation by Chained Equations (MICE) and K-Nearest Neighbors (KNN). 
- MICE was used for both moderate and high percentages of missing values due to its robustness.

### Data Distribution

- The distribution of protein quantities was visualized using histograms, boxplots, and violin plots to understand the overall distribution and identify any significant differences between conditions (treat and vehicle).

## Summary Statistics

Summary statistics provided insights into the central tendency and variability of protein quantities across different conditions and cell lines. Statistical tests were used to further explore significant differences between conditions.

## Hypothesis Testing

- **T-test**: Evaluated if there were significant differences between vehicle and treatment conditions.
- **Wilcoxon Test**: Conducted as a non-parametric alternative to the t-test to accommodate potential non-normal data distribution.

The Wilcoxon test identified significant differences between conditions, highlighting proteins of interest for further analysis.

## Clustering

- **Hierarchical Clustering**: Used to group proteins based on their quantification profiles, resulting in three distinct clusters.
- **K-means Clustering**: Further refined the analysis by clustering proteins into four groups based on standardized data, with visualizations provided through PCA plots.

## Conclusion

The analysis revealed subtle differences between treated and vehicle conditions and identified specific proteins of interest. Further investigation is required to explore these proteins in greater detail and validate potential biomarkers or therapeutic targets.

## Files

- `Protein_Quantification_Analysis.Rmd`: RMarkdown file containing the code and analysis.
- `TestDataSet_protein.txt`: Example dataset used for analysis.

## Requirements

Ensure the following R packages are installed:
- `dplyr`
- `tidyr`
- `ggplot2`
- `mice`
- `DMwR2`
- `caret`
- `RANN`
- `FactoMineR`
