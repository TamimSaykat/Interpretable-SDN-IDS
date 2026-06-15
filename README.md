<div align="center">

# OptiXGB-IDS  
### An Efficient and Interpretable Intrusion Detection Framework for Software-Defined Networks with Multi-Class Imbalanced Data Using Genetic and GAN-Based Optimization
<p>
  <img src="https://img.shields.io/badge/Task-SDN%20Intrusion%20Detection-0A66C2?style=for-the-badge">
  <img src="https://img.shields.io/badge/Framework-OptiXGB--IDS-6A5ACD?style=for-the-badge">
  <img src="https://img.shields.io/badge/Optimization-GAN%20%2B%20GA-EF6C00?style=for-the-badge">
  <img src="https://img.shields.io/badge/Explainability-SHAP%20%7C%20LIME%20%7C%20Morris-00897B?style=for-the-badge">
</p>

<p>
  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/XGBoost-Optimized%20Classifier-FF6600?style=flat-square">
  <img src="https://img.shields.io/badge/scikit--learn-ML%20Pipeline-F7931E?style=flat-square&logo=scikitlearn&logoColor=white">
  <img src="https://img.shields.io/badge/PyTorch-WGAN--GP-EE4C2C?style=flat-square&logo=pytorch&logoColor=white">
  <img src="https://img.shields.io/badge/XAI-SHAP%20%2B%20LIME-2E7D32?style=flat-square">
</p>

**OptiXGB-IDS** is a leakage-free, lightweight, and interpretable intrusion detection framework for imbalanced multi-class Software-Defined Network traffic.

</div>

---

## Overview

Software-Defined Networks are highly vulnerable to modern cyber-attacks because the centralized controller and programmable interfaces introduce critical attack surfaces. Intrusion detection in SDN environments is further complicated by severe class imbalance, high-dimensional traffic features, minority attack scarcity, and limited interpretability of many high-performing models.

This repository provides the implementation associated with the manuscript:

> **An Efficient and Interpretable Intrusion Detection Framework for Software-Defined Networks with Multi-Class Imbalanced Data Using Genetic and GAN-Based Optimization**

The proposed framework, **OptiXGB-IDS**, integrates:

- leakage-free preprocessing,
- class-specific WGAN-GP-based minority attack balancing,
- ANOVA-based statistical feature filtering,
- Genetic Algorithm-based feature subset optimization,
- grid-search-optimized XGBoost classification,
- cross-validation and hold-out testing,
- reliability, uncertainty, and statistical evaluation,
- SHAP, LIME, Morris sensitivity, and permutation-based interpretability.

---

## Framework Summary

```text
Raw SDN / IDS Dataset
        │
        ▼
Leakage-Free Train-Test Split
        │
        ▼
Training-Guided Preprocessing
        ├── Encoding
        ├── Missing-value imputation
        ├── IQR-based outlier handling
        └── Standardization
        │
        ▼
Class-Specific WGAN-GP Balancing
        ├── Controlled majority downsampling
        └── Minority-class synthetic generation
        │
        ▼
Dual-Stage Feature Selection
        ├── One-way ANOVA filtering
        └── Genetic Algorithm optimization
        │
        ▼
Model Training and Optimization
        ├── Random Forest
        ├── Extra Trees
        ├── Decision Tree
        ├── KNN
        ├── MLP
        ├── CatBoost
        └── OptiXGB-IDS
        │
        ▼
Evaluation and Validation
        ├── Hold-out testing
        ├── 5-fold cross-validation
        ├── Confidence intervals
        ├── Reliability analysis
        ├── Ablation study
        └── CIC-IDS2017 benchmark validation
        │
        ▼
Explainability and Sensitivity Analysis
        ├── SHAP
        ├── LIME
        ├── Morris sensitivity analysis
        └── Permutation importance
```

---

## Key Contributions

This repository supports the main contributions of the study:

1. A leakage-free SDN intrusion detection pipeline for imbalanced multi-class traffic.
2. Class-specific WGAN-GP hybrid resampling to improve minority attack representation.
3. Dual-stage ANOVA–Genetic Algorithm feature selection for compact and discriminative feature optimization.
4. Grid-search-optimized XGBoost classifier, referred to as **OptiXGB-IDS**.
5. Comprehensive evaluation using hold-out testing, 5-fold cross-validation, reliability metrics, uncertainty quantification, ablation analysis, and additional benchmark validation.
6. Multi-level interpretability through SHAP, LIME, Morris sensitivity analysis, permutation importance, and surrogate decision-tree visualization.

---

## Datasets

The framework was evaluated on two public intrusion detection datasets.

| Dataset | Role | Description |
|---|---|---|
| InSDN | Primary dataset | SDN-specific intrusion detection benchmark with highly imbalanced multi-class traffic |
| CIC-IDS2017 | Additional benchmark | Large-scale intrusion detection dataset used to assess framework robustness beyond InSDN |

### InSDN Classes

The primary InSDN setup includes the following traffic classes:

| Class | Description |
|---|---|
| Normal | Legitimate benign network traffic |
| Probe | Network scanning and reconnaissance |
| DoS | Single-source denial-of-service traffic |
| DDoS | Distributed denial-of-service traffic |
| BFA | Brute-force authentication attack |
| Web-Attack | HTTP-based web application attack |
| BOTNET | Botnet-generated malicious traffic |
| U2R | User-to-root privilege escalation attempt |

---

## Selected Feature Set

The final OptiXGB-IDS model uses a compact subset of **13 discriminative traffic-flow features** selected through ANOVA filtering followed by Genetic Algorithm optimization.

| Feature | Description |
|---|---|
| `Bwd Pkts/s` | Backward packets per second |
| `Src Port` | Source port |
| `Dst Port` | Destination port |
| `Pkt Len Var` | Packet length variance |
| `Pkt Len Max` | Maximum packet length |
| `Subflow Bwd Byts` | Backward subflow bytes |
| `TotLen Bwd Pkts` | Total length of backward packets |
| `Bwd Header Len` | Backward header length |
| `Init Bwd Win Byts` | Initial backward TCP window bytes |
| `Down/Up Ratio` | Download-to-upload traffic ratio |
| `Fwd Act Data Pkts` | Forward packets carrying payload |
| `Flow Duration` | Duration of the network flow |
| `Bwd IAT Min` | Minimum backward inter-arrival time |

---

## Repository Structure

A recommended repository structure is shown below. You may adapt the filenames according to your uploaded notebooks or scripts.

```text
OptiXGB-IDS/
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── README.md
│
├── notebooks/
│   ├── 01_preprocessing_and_split.ipynb
│   ├── 02_wgan_gp_balancing.ipynb
│   ├── 03_anova_ga_feature_selection.ipynb
│   ├── 04_model_training_grid_search.ipynb
│   ├── 05_evaluation_and_cross_validation.ipynb
│   ├── 06_ablation_analysis.ipynb
│   ├── 07_xai_shap_lime_analysis.ipynb
│   ├── 08_morris_permutation_sensitivity.ipynb
│   └── 09_cicids2017_validation.ipynb
│
├── src/
│   ├── preprocessing/
│   │   ├── split_data.py
│   │   ├── clean_features.py
│   │   └── leakage_free_transform.py
│   │
│   ├── balancing/
│   │   ├── wgan_gp.py
│   │   └── hybrid_resampling.py
│   │
│   ├── feature_selection/
│   │   ├── anova_filter.py
│   │   └── genetic_algorithm.py
│   │
│   ├── models/
│   │   ├── train_baselines.py
│   │   ├── train_optixgb.py
│   │   └── grid_search.py
│   │
│   ├── evaluation/
│   │   ├── metrics.py
│   │   ├── cross_validation.py
│   │   ├── confidence_intervals.py
│   │   └── reliability_analysis.py
│   │
│   ├── explainability/
│   │   ├── shap_analysis.py
│   │   ├── lime_analysis.py
│   │   ├── morris_sensitivity.py
│   │   └── permutation_importance.py
│   │
│   └── utils/
│       └── seed.py
│
├── results/
│   ├── figures/
│   ├── tables/
│   └── saved_models/
│
├── requirements.txt
├── environment.yml
├── LICENSE
└── README.md
```

---

## Methodology

### 1. Leakage-Free Preprocessing

The train and test sets are kept fully separate throughout preprocessing. All transformation parameters are learned from the training data only and then applied to the test data.

The preprocessing pipeline includes:

```text
Train-test split
    → categorical encoding
    → numeric feature alignment
    → IQR-based outlier capping
    → median imputation
    → standardization
```

This design prevents information leakage and supports fair model evaluation.

---

### 2. Class-Specific WGAN-GP Balancing

To address severe class imbalance, minority attack classes are augmented using class-specific WGAN-GP models.

The balancing strategy includes:

```text
Controlled downsampling of majority classes
        +
Class-specific WGAN-GP generation for minority classes
        ↓
Balanced training set
```

Unlike global oversampling, each minority class is modeled independently to preserve class-specific traffic characteristics and reduce the risk of mode mixing.

---

### 3. Dual-Stage Feature Selection

Feature selection is performed in two stages.

#### Stage 1: ANOVA Filtering

One-way ANOVA is used to rank features according to class-discriminative power. The filtering stage applies:

```text
F-statistic ranking
False Discovery Rate correction
Effect-size thresholding
Top feature preselection
```

#### Stage 2: Genetic Algorithm Optimization

The Genetic Algorithm searches for compact and interaction-aware feature subsets. The fitness function is based on cross-validated macro-F1 score.

```text
Candidate feature subset
        → classifier evaluation
        → macro-F1 fitness score
        → selection, crossover, mutation
        → optimized feature subset
```

The final selected feature subset contains 13 traffic-flow descriptors.

---

### 4. OptiXGB-IDS Classifier

The final proposed model is a grid-search-optimized XGBoost classifier.

```text
Selected 13 features
        ↓
Grid-search-optimized XGBoost
        ↓
OptiXGB-IDS
        ↓
Multi-class intrusion prediction
```

The optimized configuration includes regularized boosting, controlled tree depth, subsampling, and multiclass probability prediction.

---

## Baseline Models

The proposed OptiXGB-IDS model is compared with the following baseline classifiers:

| Model | Type |
|---|---|
| Random Forest | Ensemble tree model |
| Extra Trees | Randomized ensemble tree model |
| Decision Tree | Single interpretable tree |
| KNN | Instance-based classifier |
| MLP | Neural network classifier |
| CatBoost | Gradient boosting model |
| OptiXGB-IDS | Proposed optimized XGBoost model |

---

## Experimental Protocol

The evaluation protocol includes:

```text
80:20 leakage-free train-test split
5-fold cross-validation
Grid-search hyperparameter optimization
Hold-out test evaluation
Reliability analysis
Confidence interval estimation
Prediction confidence analysis
Ablation study
CIC-IDS2017 benchmark validation
Explainable AI analysis
```

The evaluation emphasizes macro-averaged metrics because the dataset is highly imbalanced and minority attack detection is critical for intrusion detection.

---

## Reported Results

### InSDN Test Performance

| Model | Precision | Recall | Macro-F1 | Accuracy |
|---|---:|---:|---:|---:|
| Random Forest | 0.9111 | 0.9947 | 0.9467 | 99.86% |
| Decision Tree | 0.8182 | 0.9873 | 0.8672 | 99.73% |
| KNN | 0.8597 | 0.9975 | 0.9073 | 99.80% |
| MLP | 0.8419 | 0.9896 | 0.8928 | 99.65% |
| CatBoost | 0.9538 | 0.9951 | 0.9712 | 99.88% |
| Extra Trees | 0.9083 | 0.9981 | 0.9445 | 99.90% |
| **OptiXGB-IDS** | **0.9618** | **0.9951** | **0.9775** | **99.87%** |

---

### Cross-Validation Stability

| Model | Mean Accuracy ± SD |
|---|---:|
| Random Forest | 0.9950 ± 0.0009 |
| Decision Tree | 0.9931 ± 0.0008 |
| KNN | 0.9919 ± 0.0012 |
| MLP | 0.9890 ± 0.0011 |
| CatBoost | 0.9964 ± 0.0006 |
| Extra Trees | 0.9971 ± 0.0005 |
| **OptiXGB-IDS** | **0.9973 ± 0.0003** |

---

### Reliability Metrics

| Metric | OptiXGB-IDS |
|---|---:|
| Cohen's kappa | 0.9982 |
| Brier score | 0.0024 |
| Test AUC | 1.0000 |
| Per-flow inference time | 0.026312 ms |

---

### Additional Benchmark Validation

| Dataset | Best Model | Test Accuracy |
|---|---|---:|
| InSDN | OptiXGB-IDS | 99.87% |
| CIC-IDS2017 | OptiXGB-IDS | 98.70% |

---

## Ablation Study

The ablation study compares GAN-based balancing with SMOTE-based alternatives.

| Setting | Description |
|---|---|
| SMOTE with default parameters | Standard SMOTE oversampling without model-level tuning |
| SMOTE with grid search | SMOTE with optimized classifier parameters |
| GAN with default parameters | GAN-based balancing without full grid-search optimization |
| Proposed GAN + grid search | WGAN-GP balancing with optimized classifier configuration |

The results show that GAN-based balancing provides stronger performance than SMOTE-based oversampling, and the proposed GAN + grid-search configuration provides the most effective final detection pipeline.

---

## Explainability and Sensitivity Analysis

The repository includes multiple interpretability modules.

### Global Explanation

SHAP is used to identify globally important traffic features. The most influential features include:

```text
Init Bwd Win Byts
Src Port
Dst Port
Fwd Header Len
Flow Pkts/s
Protocol
```

### Local Explanation

LIME is used to explain class-specific individual predictions by showing how thresholded feature conditions support or oppose the predicted class.

### Sensitivity Analysis

Morris global sensitivity analysis and permutation importance are used to validate whether the model depends on a stable and operationally meaningful set of traffic descriptors.

The combined explainability results indicate that OptiXGB-IDS relies on compact, interpretable, and security-relevant flow features rather than diffuse or unstable decision cues.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/OptiXGB-IDS.git
cd OptiXGB-IDS
```

Create a virtual environment:

```bash
python -m venv optixgb_env
source optixgb_env/bin/activate
```

For Windows:

```bash
optixgb_env\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Main Dependencies

```text
python >= 3.10
numpy
pandas
scikit-learn
xgboost
catboost
torch
matplotlib
seaborn
scipy
shap
lime
SALib
imbalanced-learn
tqdm
joblib
```

---

## Quick Start

### 1. Preprocess the Dataset

```bash
python src/preprocessing/leakage_free_transform.py
```

### 2. Apply WGAN-GP Balancing

```bash
python src/balancing/hybrid_resampling.py
```

### 3. Run ANOVA–GA Feature Selection

```bash
python src/feature_selection/anova_filter.py
python src/feature_selection/genetic_algorithm.py
```

### 4. Train OptiXGB-IDS

```bash
python src/models/train_optixgb.py
```

### 5. Evaluate the Model

```bash
python src/evaluation/metrics.py
python src/evaluation/cross_validation.py
python src/evaluation/reliability_analysis.py
```

### 6. Run Explainability Analysis

```bash
python src/explainability/shap_analysis.py
python src/explainability/lime_analysis.py
python src/explainability/morris_sensitivity.py
python src/explainability/permutation_importance.py
```

---

## Reproducibility Notes

To support reproducibility:

```text
All random seeds are fixed where applicable.
Train and test sets are separated before preprocessing.
Preprocessing parameters are fitted only on the training set.
Synthetic samples are generated only for the training set.
Feature selection is performed only on the balanced training set.
Model selection is performed through cross-validation on training data.
The hold-out test set remains untouched until final evaluation.
CIC-IDS2017 is used as an additional benchmark validation dataset.
```

---

## Recommended Citation

If you use this code or build upon this repository, please cite the associated manuscript:

```bibtex
@article{saykat2026optixgbids,
  title   = {An Efficient and Interpretable Intrusion Detection Framework for Software-Defined Networks with Multi-Class Imbalanced Data Using Genetic and GAN-Based Optimization},
  author  = {Saykat, Md. Tamim Hasan and Haque, Md. Ehsanul and Al Farid, Fahmid and Hossen, Rakib and Uddin, Jia and Abdul Karim, Hezerul},
  journal = {Under Review},
  year    = {2026}
}
```

---

## Code Availability

The source code, preprocessing pipeline, class-specific WGAN-GP balancing module, ANOVA–Genetic Algorithm feature selection, optimized XGBoost training, baseline comparisons, cross-validation, ablation experiments, reliability analysis, uncertainty quantification, CIC-IDS2017 validation, and explainability scripts are available in this repository.

Repository URL:

```text
https://github.com/<your-username>/OptiXGB-IDS
```

---

## Ethical and Responsible Use

This repository is intended for academic research on intrusion detection in Software-Defined Networks and related cybersecurity environments. The code should be used only for defensive security research, benchmark evaluation, educational purposes, and authorized network-security analysis.

The framework must not be used for unauthorized access, malicious traffic generation, attack automation, or any activity that violates legal or ethical cybersecurity standards.

---

## License

This project is released under the license specified in the repository.

See the [`LICENSE`](LICENSE) file for details.

---

## Contact

For questions, collaboration, or implementation-related inquiries, please contact the corresponding authors listed in the manuscript.

<div align="center">

---

### OptiXGB-IDS  
**Leakage-Free, Lightweight, and Interpretable SDN Intrusion Detection**

</div>
