# Kidney Single-Cell Logistic Regression Analysis

## Overview
This project applies **binary logistic regression** to a human kidney single-cell RNA-seq dataset to model a global renal injury signal. Cells are labeled as **healthy** or **diseased**, where diseased includes both **acute kidney injury (AKI)** and **chronic kidney disease (CKD)**. The goal is to identify transcriptional programs associated with kidney injury using an interpretable machine learning approach.

---

## Dataset
- **Source:** CZ CELLxGENE Discover
- **Modality:** Single-cell RNA sequencing (scRNA-seq)
- **Tissue:** Human kidney
- **Disease categories:**
  - AKI
  - CKD
  - Healthy living donor
  - Healthy stone donor

For modeling purposes, AKI and CKD are combined into a single **diseased** class, while both healthy donor categories are combined into a **healthy** class.

---

## Modeling Approach

### Target Variable
A binary label (`unhealthy`) is constructed:
- `1` → AKI or CKD
- `0` → Healthy donors

### Features
- Gene expression features derived from the AnnData object
- Optional filtering to highly variable genes
- Optional pseudobulking at the donor level to reduce leakage

### Model
- **Logistic Regression**
- L2 regularization
- Class balancing to account for label imbalance
- Train/test splits performed at the **donor level**

---

## Evaluation
Model performance is evaluated using:
- ROC-AUC
- Confusion matrix
- Accuracy, precision, recall
- Cross-validation (where applicable)

These metrics assess the model’s ability to distinguish injured from healthy kidney cells while maintaining interpretability.

---

## Motivation
Logistic regression provides a strong, interpretable baseline for single-cell disease modeling. This analysis emphasizes:
- Biological interpretability of coefficients
- Proper handling of confounders and data leakage
- Reproducible ML practices in bioinformatics

---


