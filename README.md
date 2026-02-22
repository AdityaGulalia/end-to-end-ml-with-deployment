Adult Income Classification
End-to-End Machine Learning System
Project Summary

Designed and implemented a modular end-to-end machine learning system to predict whether an individual's annual income exceeds $50K using the Adult Census dataset (UCI Machine Learning Repository).

The project focuses on production-style ML architecture, reproducibility, and scalable system design rather than notebook-based experimentation.

Key Contributions

Architected a layered ML system with clear separation between configuration, data ingestion, preprocessing, modeling, evaluation, and inference.

Implemented a leakage-safe preprocessing pipeline using scikit-learn’s Pipeline and ColumnTransformer.

Engineered automated handling of missing categorical values and structured numerical transformations.

Designed interchangeable model abstraction supporting Logistic Regression, Decision Tree, and Random Forest.

Built a reproducible training workflow with configuration-driven experimentation.

Developed a modular inference layer capable of consuming structured input and returning probability outputs.

Technical Stack

Python

pandas

NumPy

scikit-learn

Matplotlib / Seaborn

ML Techniques Applied

Binary classification

Feature encoding (One-Hot Encoding)

Numerical scaling (StandardScaler)

Missing value imputation

Train-test stratified splitting

Pipeline-based transformation enforcement

Model comparison

ROC-AUC evaluation

Architectural Highlights

Single-responsibility module design

Deterministic data flow between layers

Configuration-driven model selection

Encapsulated preprocessing logic

Clear separation between training and inference workflows

Dataset

Adult Census Income Dataset
UCI Machine Learning Repository
https://archive.ics.uci.edu/ml/datasets/adult

~48,000 records | Mixed categorical & numerical features | Real census data

Outcome

Delivered a structured, extensible ML codebase demonstrating production-aligned engineering practices suitable for integration into future API-based deployment systems.
