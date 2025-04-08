# FlavourAI: Personalized Dish Recommendation System

A Data-Driven Approach to Recipe Discovery and Nutritional Insights

## Project Overview
FlavourAI is a smart recipe recommendation system designed to help users discover dishes based on dietary preferences, review sentiment, and nutritional goals. In Milestone 2, we focused on building machine learning models that analyze recipe metadata and user reviews to predict high-protein recipes and identify highly rated dishes.

---

## Milestone 2 Goals
- Engineer meaningful features from keywords and review texts.
- Train classification models to detect high-protein recipes and high-rating reviews.
- Evaluate models using robust metrics.
- Lay the foundation for an intelligent chatbot and dashboard in Milestone 3.

---

## Feature Engineering
- **Keywords Column**: Preprocessed and transformed using TF-IDF to capture contextual nutritional tags.
- **Review Column**: Cleaned using regex and transformed using TF-IDF for sentiment classification.
- **Labeling**:
  - High-Protein Label: 1 if `ProteinContent_Level` ≥ 3
  - High-Rating Label: 1 if `Rating` = 5

---

## Feature Selection
- Removed low-variance and redundant features.
- Applied Chi-Square tests and correlation checks.
- Controlled dimensionality using `max_features=1000` in TF-IDF.

---

## Modeling

### A. High-Protein Prediction (from Keywords)
- Models: Logistic Regression, Decision Tree, Random Forest
- Input: TF-IDF of recipe `Keywords`

### B. High-Rating Prediction (from Reviews)
- Models: Logistic Regression, Decision Tree, Random Forest
- Input: TF-IDF of user `Review` text

---

## Training & Evaluation
- **Split**: 70% train, 15% validation, 15% test
- **Cross-validation**: 5-fold
- **Metrics**: Accuracy, Precision, Recall, F1-Score, ROC-AUC
- **Visualization**: ROC Curves for all models

---

## Model Performance Summary

| Task                         | Model               | Accuracy | Precision | Recall | F1-Score | AUC  |
|------------------------------|---------------------|----------|-----------|--------|----------|------|
| Protein Prediction (Keywords)| Logistic Regression | 0.78     | 0.79      | 0.93   | 0.85     | 0.79 |
|                              | Decision Tree       | 0.71     | 0.73      | 0.92   | 0.82     | 0.63 |
|                              | Random Forest       | 0.72     | 0.72      | 1.00   | 0.84     | 0.76 |
| Review Sentiment Prediction  | Logistic Regression | 0.77     | 0.79      | 0.93   | 0.86     | 0.79 |
|                              | Decision Tree       | 0.71     | 0.73      | 0.92   | 0.82     | 0.63 |
|                              | Random Forest       | 0.72     | 0.72      | 1.00   | 0.84     | 0.76 |

---

## Visual Interpretation

- Logistic Regression had the highest AUC (~0.79), best overall performance.
- Random Forest performed well in recall but had slightly lower precision.
- Decision Trees underperformed and showed signs of overfitting.
- ROC curves and confusion matrices confirmed model behaviors.

---

## Chatbot & Dashboard Integration (Next Phase)

In the next milestone, we will build a chatbot that accepts natural queries like:  
“I want to eat high protein spicy chicken”  
and returns the top 10 recipe recommendations by parsing input and matching it to:

- `Keywords`, `Name`, `RecipeCategory`
- Nutritional levels: `ProteinContent_Level`, `Calories_Level`, etc.

These models will also be integrated into a Streamlit-based dashboard for live exploration.

---

## Deliverables

- Cleaned datasets with nutritional and review features  
- Trained classification models (high-protein + sentiment)  
- Evaluation metrics and ROC curves  
- Logic for chatbot-based filtering  
- Milestone 2 Final Report  
- Repository link with documentation  

---

## GitHub Repositories

- Main Repository: https://github.com/AdityaAdke123/Milestone_Sem2_IDS  
- Milestone 2 Scripts: https://github.com/AdityaAdke123/Milestone-2_Project
