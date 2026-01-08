🏥 Predicting Patient Mortality — ML System with Explainability
Overview

This project implements an end-to-end machine learning system to predict patient mortality risk using structured healthcare data.
The focus is not only on model accuracy, but also on engineering discipline, evaluation rigor, and explainability, making the system suitable for real-world decision support.

The project follows a production-style ML workflow:

Offline experimentation with multiple algorithms

Metric-driven model selection

Promotion of a single best-performing model for inference

Explainability using SHAP to support interpretability in healthcare settings

🎯 Problem Statement

Patient mortality prediction is a critical task in healthcare, where early risk identification can support clinical decision-making and resource allocation.

Key challenges addressed:

Class imbalance (mortality events are rare)

Model interpretability in a regulated domain

Threshold selection for precision–recall trade-offs

Generalization vs overfitting

🧠 ML & Engineering Approach
1. Data Analysis & Feature Understanding

Exploratory data analysis to understand demographic and clinical features

Correlation analysis to identify feature relationships

Visualization-driven insight generation

2. Multiple Model Experimentation

To avoid bias toward a single approach, multiple algorithms were implemented and evaluated:

Logistic Regression (baseline)

Decision Tree

Random Forest

All models share a common interface, enabling consistent training, evaluation, and comparison.

3. Model Evaluation Strategy

F1-score used as the primary metric to handle class imbalance

Threshold-aware evaluation to balance recall vs precision

Overfitting analysis using train vs validation metrics

4. Model Selection & Promotion

All candidate models are trained and evaluated offline

The best-performing model is promoted to production

Non-selected models remain available for future experimentation and retraining

5. Explainability (SHAP)

SHAP values used to interpret feature impact


📊 Explainability & Visualizations

The project includes:

Correlation heatmaps

Model performance comparisons

Training vs validation curves

SHAP feature importance and summary plots

These artifacts support model debugging, trust, and communication with non-ML stakeholders.

🏗️ Production Considerations

Model Retraining
Models can be retrained periodically as new patient data becomes available.

Threshold Calibration
Decision thresholds are configurable to balance recall vs precision depending on clinical risk tolerance.

Explainability
SHAP-based explanations enable inspection of feature contributions for individual predictions.

Failure Modes & Risks

Data drift due to changing patient demographics

Missing or noisy clinical inputs

Bias amplification if retraining data is skewed

🛠️ Tech Stack

Machine Learning

Python

Scikit-learn

SHAP

NumPy, Pandas

Backend / Serving

FastAPI

Pydantic

Joblib

Visualization

Matplotlib

Seaborn

Supports transparency and trust in predictions

Enables clinical review of model behavior
