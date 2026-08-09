# CLARANS Clustering: Randomized Medoid-Based Segmentation

### A Python Implementation of CLARANS for Data Mining and University Admission Analysis

<p>
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=for-the-badge&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge&logo=matplotlib&logoColor=white">
  <img src="https://img.shields.io/badge/Unsupervised%20Learning-Clustering-orange?style=for-the-badge">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white">
</p>

---

## 📌 Overview

This project re-implements the **CLARANS (Clustering Large Applications
based upon RANdomized Search)** clustering algorithm in Python.

The implementation is based on the research paper:

> **CLARANS: A Method for Clustering Objects for Spatial Data Mining**  
> Raymond T. Ng and Jiawei Han, Member, IEEE Computer Society

The project applies CLARANS to **university admissions data** to identify
groups of universities with similar application acceptance and enrollment
patterns.

The implementation includes:

- Data preprocessing
- Exploratory data analysis
- CLARANS clustering from scratch
- Randomized medoid search
- Distance-based cost calculation
- Hyperparameter tuning using grid search
- Cluster visualization with Matplotlib
- Interpretation of university admission and enrollment patterns

---

# 🎯 Problem Statement

In the context of university admissions, institutions need to understand
patterns and relationships between:

1. The number of students applying.
2. The number of applications accepted.
3. The number of students who ultimately enroll.

Understanding these relationships can help universities analyze admission
strategies, manage resources, and identify enrollment patterns.

For this project, universities are clustered primarily using:

- **Number of applications accepted**
- **Number of students enrolled after acceptance**

The objective is to group universities exhibiting similar admission and
enrollment behavior.

This allows us to identify patterns such as:

- Universities receiving and accepting large numbers of applications.
- Universities with relatively high enrollment.
- Universities with many accepted applicants but comparatively lower enrollment.
- Universities exhibiting similar admission and enrollment characteristics.

---

# 🧠 Why CLARANS?

CLARANS is a randomized clustering algorithm based on the **k-medoids**
concept.

Unlike centroid-based clustering approaches, CLARANS uses **medoids**, which
are actual observations from the dataset, and explores alternative medoid
configurations through randomized neighborhood search.

The algorithm was selected because it provides:

### Randomized Search

CLARANS explores different possible clustering configurations by randomly
selecting neighboring solutions.

### Scalability

CLARANS is designed to be more scalable than traditional k-medoids and is
therefore suitable for larger datasets.

### Interpretability

Because clusters are represented by medoids, the resulting groups can be
interpreted based on actual observations in the dataset.

---

# ⚙️ CLARANS Algorithm

The implementation follows the following workflow:

```text
                    Dataset
                       │
                       ▼
              Data Preprocessing
                       │
                       ▼
             Random Medoid Selection
                       │
                       ▼
               Cluster Assignment
                       │
                       ▼
                Cost Calculation
                       │
                       ▼
             Random Neighbor Search
                       │
                  ┌────┴────┐
                  │         │
             Better Cost?   │
                  │         │
                 Yes        No
                  │         │
                  ▼         │
          Update Medoids    │
                  │         │
                  └────┬────┘
                       ▼
                Repeat Search
                       │
                       ▼
              Best Configuration
                       │
                       ▼
              Cluster Visualization
