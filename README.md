# Adult Income Classification  
### Production-Structured End-to-End Machine Learning System

---

## Overview

This project implements a modular, production-aligned machine learning system to predict whether an individual earns more than \$50,000 annually using real U.S. Census data from the UCI Machine Learning Repository.

The objective of this repository is to demonstrate structured ML system design — emphasizing architectural clarity, reproducibility, and separation of concerns across the full ML lifecycle.

---

## Dataset

**Adult Census Income Dataset**  
UCI Machine Learning Repository  
https://archive.ics.uci.edu/ml/datasets/adult  

- ~48,000 records  
- Mixed categorical and numerical features  
- Missing values encoded as `"?"`  
- Moderate class imbalance  
- Real census-derived demographic data  

---

## Problem Statement

Develop a supervised classification system capable of estimating the probability that an individual earns more than \$50K annually based on structured demographic attributes.

The system is designed to:

- Prevent data leakage  
- Enforce consistent preprocessing  
- Support interchangeable models  
- Maintain strict modular separation  
- Remain extensible for future production integration  

---

## Architecture

The project follows a layered, single-responsibility design:

```
src/
├── config.py        # Central configuration
├── data_loader.py   # Data ingestion
├── preprocess.py    # Transformation pipelines
├── model.py         # Model abstraction
├── train.py         # Training orchestration
├── evaluate.py      # Performance evaluation
├── predict.py       # Inference interface
└── utils.py         # Shared utilities

main.py              # System entry point
```

Data flows deterministically through the system:

```
CONFIG → DATA → PREPROCESS → MODEL → TRAIN → EVALUATE → SAVE → PREDICT
```

Each module returns explicit outputs consumed by the next stage, ensuring traceable and predictable behavior.

---

## Processing Strategy

All transformations are encapsulated within a scikit-learn `Pipeline` using `ColumnTransformer`.

**Numerical Features**
- Median imputation  
- Standard scaling  

**Categorical Features**
- Mode imputation  
- One-hot encoding with unknown-category handling  

This guarantees identical behavior during training and inference while eliminating leakage risk.

---

## Models Implemented

- Logistic Regression  
- Decision Tree  
- Random Forest  

Model selection is configuration-driven and does not require structural modification of the training pipeline.

---

## Evaluation Metrics

- Accuracy  
- Precision  
- Recall  
- F1 Score  
- ROC-AUC  

Evaluation is decoupled from training to preserve architectural integrity.

---

## Technical Stack

- Python  
- pandas  
- NumPy  
- scikit-learn  
- Matplotlib  
- Seaborn  

---

## Design Principles Applied

- Single Responsibility Principle  
- Configuration-driven experimentation  
- Encapsulated preprocessing logic  
- Clear training vs inference separation  
- Modular, extensible architecture  
- Deterministic data flow  

---

## Future Scope

The system is structured to support:

- Hyperparameter optimization  
- Threshold tuning  
- Feature importance analysis  
- API integration  
- Containerized deployment  

Deployment will be implemented in a future phase.

---

## Summary

This repository demonstrates the transition from notebook-centric experimentation to production-oriented machine learning system design. It reflects engineering discipline, modular architecture, and scalable ML implementation practices.
