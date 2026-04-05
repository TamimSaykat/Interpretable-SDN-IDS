<div align="center">

# OptiXGB-IDS

**Forthcoming research companion for interpretable, multiclass SDN intrusion detection under severe data imbalance**

*Companion repository for the manuscript*  
**An Efficient and Interpretable Intrusion Detection Framework for Software-Defined Networks with Multi-Class Imbalanced Data Using Genetic and GAN-Based Optimization**

![Paper](https://img.shields.io/badge/Paper-Forthcoming-1F6FEB)
![Code](https://img.shields.io/badge/Code-Release%20After%20Publication-8250DF)
![Status](https://img.shields.io/badge/Status-Pre--publication-6E7781)
![Repository](https://img.shields.io/badge/Repository-Companion%20Page-0A7EA4)

</div>

> **Availability notice**  
> This repository is currently maintained as a pre-publication companion page. Public release of the implementation will follow once the article is published, appears online, or public dissemination is otherwise permitted.

---

## Overview

`OptiXGB-IDS` is the companion repository for a forthcoming journal paper on interpretable and imbalance-aware intrusion detection in software-defined networks (SDNs). The study centers on a hybrid research pipeline that combines leakage-free preprocessing, class-specific generative balancing, dual-stage feature selection, model optimization, and explainability-driven analysis for multiclass intrusion detection.

At this stage, the repository intentionally functions as a citation anchor and project landing page. The public codebase and reproducibility materials are being prepared for release at the appropriate stage of the publication process.

## Why this work matters

Intrusion detection in SDN environments must address more than headline accuracy. In practice, research-grade IDS frameworks must remain reliable under class imbalance, computationally practical, and sufficiently interpretable to support operational trust, failure analysis, and scientific reproducibility.

This project is designed around that objective: a methodologically rigorous and transparently documented companion repository for a publication-oriented research contribution.

## Key contributions

- Intrusion detection for software-defined networks under severe multiclass imbalance
- A generative balancing strategy tailored to minority attack classes
- Dual-stage feature selection combining statistical screening and genetic optimization
- Comparative model optimization and benchmark-oriented evaluation
- Explainability and sensitivity analysis to support transparent interpretation

## Method overview

The public release is planned to document the following study pipeline:

1. **Leakage-free preprocessing**  
   Training-guided encoding, imputation, outlier handling, and feature scaling.

2. **Training-set balancing**  
   Class-specific generative resampling for minority classes with controlled treatment of dominant classes.

3. **Feature selection**  
   A two-stage strategy combining ANOVA-based filtering and genetic search to obtain a compact, discriminative feature subset.

4. **Model training and optimization**  
   Baseline comparison, hyperparameter search, and final model selection for multiclass SDN intrusion detection.

5. **Interpretability and robustness analysis**  
   Explainability, sensitivity, and permutation-based analysis aligned with the study’s methodology.

## Planned repository structure

```text
OptiXGB-IDS/
├── README.md
├── LICENSE
├── docs/
│   ├── figures/
│   ├── release-notes/
│   └── reproducibility/
├── paper/
│   ├── citation/
│   └── publication-metadata/
├── configs/
├── data/
│   └── dataset-access-instructions/
├── src/
│   ├── preprocessing/
│   ├── balancing/
│   ├── feature_selection/
│   ├── models/
│   ├── explainability/
│   └── evaluation/
├── notebooks/
├── scripts/
└── results/
```

## Planned public release

Subject to publication and release permissions, the public repository is expected to include:

- preprocessing and dataset preparation utilities
- balancing, feature-selection, and model-training modules
- evaluation and interpretability workflows
- experiment configuration files
- reproducibility notes for tables, figures, and ablation studies
- selected trained models or checkpoints, where appropriate

## Installation

The implementation is **not yet public**.

A complete installation guide will be added at the time of public release. The release package is expected to include:

- environment specification files
- pinned dependency versions
- dataset preparation instructions
- experiment configuration files
- reproducibility notes aligned with the manuscript

## Usage

Executable usage examples are being prepared and will appear when the repository is officially released.

Planned documentation will include:

- end-to-end training workflows
- evaluation and benchmarking commands
- interpretability examples
- guidance for loading released checkpoints or models, where applicable
- reproduction notes for figures, tables, and ablation studies

## Datasets and requirements

The study is based on public benchmark datasets relevant to SDN and network intrusion detection, including **InSDN** and **CICIDS2017**. Raw datasets will not be mirrored in this repository unless redistribution is explicitly permitted.

The public release will provide:

- official dataset references
- preprocessing and access instructions
- expected directory layout
- benchmark-specific reproducibility notes

## Availability

This repository is being prepared as the companion repository for the manuscript listed above. The paper is not yet publicly available in its final journal form, and the implementation is therefore not released at this stage.

To respect the review process and any publication, copyright, or embargo requirements, the source code, trained models where appropriate, configuration files, and detailed reproduction instructions will be released once the article is officially published, appears online, or public release is otherwise permitted by the authors and publisher.

Until then, this repository serves as a stable project page. Please **watch** or **star** the repository to receive release announcements and updates.

## Citation

Formal citation metadata will be added once the article is publicly available.

```bibtex
@article{optixgb_ids_forthcoming,
  title   = {An Efficient and Interpretable Intrusion Detection Framework for Software-Defined Networks with Multi-Class Imbalanced Data Using Genetic and GAN-Based Optimization},
  author  = {Hasan Saykat, Md. Tamim and Haque, Md. Ehsanul and Al Farid, Fahmid and Hossen, Rakib and Uddin, Jia and Abdul Karim, Hezerul},
  journal = {To be updated},
  year    = {To be updated},
  note    = {Companion repository prepared before publication; citation metadata will be updated upon release}
}
```

## Contact

For academic inquiries regarding the manuscript or the planned repository release:

- **Md. Tamim Hasan Saykat** — `2022-1-60-289@std.ewubd.edu`


## License

A repository license will be specified at the time of the public code release.

Until then, all rights to the unpublished implementation and associated materials remain with the authors.

## Acknowledgment

This repository is being prepared as a research companion to a forthcoming journal article. We also acknowledge the maintainers of the public benchmark datasets and the wider research community working on SDN security, interpretable machine learning, and trustworthy intrusion detection.
