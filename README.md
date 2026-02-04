# 🧠 Depression Risk & Intent Classifier

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Methodology](https://img.shields.io/badge/Methodology-SDLC-purple)
![Technique](https://img.shields.io/badge/Technique-SHAP_%26_SMOTE-yellow)
![Deployment](https://img.shields.io/badge/Deployment-Gradio-pink)

## 📋 Project Overview
The **Depression Risk & Intent Classifier** is a Machine Learning application developed to analyze linguistic markers associated with depression and self-harm intent.


## Requirement Analysis
**Objective:** To distinguish between general sadness and urgent psychological distress in unstructured text.



### ✅ Functional Requirements
* **Input Handling:** The system must accept unstructured text input (e.g., social media posts, journal entries) via a web interface.
* **Classification:** The model must classify inputs into distinct risk categories: *Low Risk, High Risk,* or *Urgent Intent*.
* **Explainability:** The system must generate a visual explanation (SHAP plot) highlighting the specific words that triggered the risk classification.
* **Confidence Scoring:** The UI must display the probability score (0-100%) alongside the predicted label.

### ⚖️ Non-Functional Requirements
* **Recall Optimization:** The model must prioritize **Recall** over Precision to minimize False Negatives (critical for safety in health applications).
* **Interpretability:** The decision logic must be transparent and clinically interpretable, not a "black box."
* **Latency:** Inference must occur in real-time (<2 seconds) to ensure a smooth user experience on the Gradio interface.
* **Data Privacy:** The application must process data statelessly; no user input is stored or logged to ensure anonymity.

## System Design
**Architecture:** A modular pipeline designed for reproducibility and scalability.

* **Tech Stack:**
    * **Language:** Python
    * **ML Libraries:** Scikit-Learn, Imbalanced-Learn
    * **NLP:** Spacy, NLTK
    * **UI Framework:** Gradio
* **Data Flow:** Text Input $\rightarrow$ Preprocessing (Lemmatization/Stopwords) $\rightarrow$ TF-IDF Vectorization $\rightarrow$ Classification $\rightarrow$ SHAP Explanation $\rightarrow$ UI Output.

## Implementation & Development
This phase focused on building the core logic and handling real-world data challenges.

* **Data Preprocessing:** Implemented custom tokenization to retain psychological keywords often removed by standard stopword lists.
* **Handling Class Imbalance:** Utilized **SMOTE (Synthetic Minority Over-sampling Technique)** to generate synthetic samples for the "High Risk" class, preventing model bias toward the majority class.
* **Model Selection:** Trained multiple supervised learning algorithms (Logistic Regression, Random Forest), optimizing for the minority class performance.

## Testing & Evaluation
Rigorous testing was conducted to verify that both functional and non-functional requirements were met.

* **Performance Metrics:**
    * Achieved optimal **F1-Score** and **Recall** on the validation set.
* **Explainable AI (XAI):**
    * Integrated **SHAP (SHapley Additive exPlanations)** values to validate feature importance.
    * *Result:* The model successfully identified high-risk terms (e.g., "hopeless", "forever") as top predictors.



## Deployment
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
