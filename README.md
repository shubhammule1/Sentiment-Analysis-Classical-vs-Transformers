# 🎭 Sentiment Analysis: Classical ML vs Transformers
### Comparative study of classical ML models and transformer-based sentiment analysis, highlighting accuracy, efficiency, and LoRA fine-tuning gains.
## 📌 Project Overview

This project presents a systematic **comparison** between **classical machine learning models** and **transformer-based** approaches for sentiment analysis on movie reviews.

Rather than focusing on accuracy alone, the study also evaluates training cost, inference time, parameter efficiency, and qualitative prediction behavior, revealing why higher accuracy does not always imply better sentiment understanding.
## 🧪 Notebook Details
### 🔬 01_Experimental_Benchmarking.ipynb

**Goal: Broad experimentation and failure-mode analysis**

**Models Explored:**
- Gaussian Naive Bayes
- Multinomial Naive Bayes
- Logistic Regression (CV)
- Linear SVM
- Random Forest
- XGBoost (baseline)

**Insight:**
Random Forest and XGBoost achieved ~85% accuracy but failed on long, sarcastic, and negation-heavy reviews, demonstrating that accuracy alone can be misleading for NLP tasks

### 📊 02_Classical_Sentiment_Analysis.ipynb

**Goal: Clean, production-oriented classical NLP pipeline**

**Models Included:**
- Logistic Regression (CV)
- Linear SVM
- Multinomial Naive Bayes

GaussianNB is excluded due to incompatibility with sparse TF-IDF vectors.

### 🤗 03_BERT_and_LoRA.ipynb

**Goal: Accuracy vs efficiency in transformer fine-tuning**

**Techniques:**
- Full fine-tuning of **DistilBERT**
- Parameter-efficient fine-tuning using **LoRA (PEFT)**

## 🧰 Tech Stack
### Core:
- Python 3.9+
- NumPy, Pandas
### NLP & Preprocessing:
- NLTK (tokenization, stopwords, stemming)
- contractions
- TF-IDF Vectorization
### Classical Machine Learning:
- LogisticRegressionCV
- LinearSVC
- Multinomial Naive Bayes
- Gaussian Naive Bayes (experimental only)
- Random Forest (experimental only)
- XGBoost (experimental only)

### Deep Learning & Transformers:
- PyTorch
- Hugging Face Transformers
- DistilBERT (Sequence Classification)
### Parameter-Efficient Fine-Tuning:
- PEFT (LoRA)

## 📈 Model Performance Summary
### ✅ Classical Models

| Model                    | Accuracy (%) | 
|--------------------------|--------------
| Logistic Regression (CV) | **89.65**    |
| Linear SVM               | 89.18        | 
| Multinomial Naive Bayes  | 86.27        |

### 🤗 Transformer Models
| Metric | Full Fine-Tuning (DistilBERT) | LoRA Fine-Tuning |
|:------ |:----------------------------:|:----------------:|
| Validation Accuracy | **89.11%** | 87.11% |
| F1 Score | **0.8906** | 0.8732 |
| Trainable Parameters | 66.9M | **739K** |
| Training Time | 14.92 minutes | **4.84 minutes** |

✅ **98.9% parameter reduction**

✅ **3.08× faster training** with minimal performance loss
## 🔍 Key Insights

- ✅ Logistic Regression remains a **strong and reliable NLP baseline**
- ⚖️ Tree-based models struggle with sparse high-dimensional text representations
- 🚀 LoRA delivers **near-BERT performance at a fraction of computational cost**
- 🧠 Evaluation must consider **error behavior**, not just aggregate metrics

## ✅ Conclusion
This repository demonstrates that **well-designed classical models remain competitive**, while **modern techniques like LoRA enable efficient scaling to transformer-level performance** under real-world constraints.






