# 🧠 Depression Risk & Intent Classifier

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Deployment](https://img.shields.io/badge/Deployment-Gradio-pink)

## 📋 Project Overview
The **Depression Risk & Intent Classifier** is a Machine Learning application developed to analyze linguistic markers associated with depression and self-harm intent.

This project was executed following the **Software Development Life Cycle (SDLC)**, ensuring a structured approach from requirement analysis to deployment and maintenance.

[attachment_0](attachment)

---

## Phase 1: Requirement Analysis & Planning
**Objective:** To distinguish between general sadness and urgent psychological distress in unstructured text.

* **Problem Statement:** Standard sentiment analysis fails to capture the nuance of "intent" in mental health contexts.
* **Key Requirement:** The model must prioritize **Recall** (minimizing False Negatives) to ensure high-risk cases are not missed.
* **Ethical Constraint:** The system must explain its reasoning (XAI) to be useful in a clinical support setting.

## Phase 2: System Design
**Architecture:** A modular pipeline designed for reproducibility and scalability.

* **Tech Stack:**
    * **Language:** Python
    * **ML Libraries:** Scikit-Learn, Imbalanced-Learn
    * **NLP:** Spacy, NLTK
    * **UI Framework:** Gradio
* **Data Flow:** Text Input $\rightarrow$ Preprocessing (Lemmatization/Stopwords) $\rightarrow$ TF-IDF Vectorization $\rightarrow$ Classification $\rightarrow$ SHAP Explanation $\rightarrow$ UI Output.

## Phase 3: Implementation & Development
This phase focused on building the core logic and handling real-world data challenges.

* **Data Preprocessing:** Implemented custom tokenization to retain psychological keywords often removed by standard stopword lists.
* **Handling Class Imbalance:** Utilized **SMOTE (Synthetic Minority Over-sampling Technique)** to generate synthetic samples for the "High Risk" class, preventing model bias toward the majority class.
* **Model Selection:** Trained multiple supervised learning algorithms (Logistic Regression, Random Forest), optimizing for the minority class performance.

## Phase 4: Testing & Evaluation
Rigorous testing was conducted to ensure model reliability and interpretability.

* **Performance Metrics:**
    * Optimized for **F1-Score** and **Recall** rather than raw Accuracy.
* **Explainable AI (XAI):**
    * Integrated **SHAP (SHapley Additive exPlanations)** values to validate feature importance.
    * *Result:* The model successfully identified high-risk terms (e.g., "hopeless", "forever") as top predictors.



## Phase 5: Deployment
The model was packaged into an interactive web application for end-user accessibility.

* **Interface:** Built with **Gradio** to allow real-time text analysis.
* **Usage:** Users can input text strings and receive an immediate probabilistic risk assessment alongside the confidence score.

## Phase 6: Maintenance & Future Scope
* **Current Status:** V1.0 (Prototype).
* **Future Improvements:**
    * Integration with Transformer models (BERT/RoBERTa) for deeper context understanding.
    * API development for integration with telehealth platforms.

---

## ⚠️ Ethical Disclaimer
**This tool is for educational and research purposes only.** It is **not** a diagnostic tool and should not be used as a substitute for professional medical advice, diagnosis, or treatment.

## 🤝 Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

---
*Created by [Olorunfemi Babalola](https://linkedin.com/in/olorunfemi-babalola) - MSc Data Science & AI Candidate*
