# 🍽️ Yelp Reviews Analytics  

Machine learning and NLP project analyzing Yelp reviews to classify sentiment and discover themes.  
End-to-end analysis using **traditional ML, RNNs, topic modeling, and transformers** — showcasing the evolution of NLP approaches.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![NLP](https://img.shields.io/badge/NLP-4B8BBE?style=for-the-badge)

---

## Problem  
Yelp reviews contain valuable but unstructured insights about customer experience.  
The goal is to transform this text into **structured sentiment predictions and themes**, comparing multiple NLP approaches from baselines to modern LLMs.

---

## Method  

**File 1 — Sentiment Analysis (Traditional ML)**  
- **Vectorizers:** CountVectorizer, TF-IDF  
- **Models:** Naïve Bayes, SVM  
- **Baseline:** VADER (lexicon)  
- **Metric:** Accuracy  

**File 2 — Deep Learning (RNNs)**  
- **Models:** GRU, LSTM  
- **Embeddings:** Trainable vs frozen pre-trained  
- **Metric:** Accuracy  

**File 3 — Topic Modeling (Unsupervised)**  
- **Model:** Zero-shot topic modeling + hierarchical clustering  
- **Focus:** Discovering bilingual (Spanish/English) patterns, service-related themes  
- **Deliverables:** Graphs & visuals of clustered topics  

**File 4 — Transformers (Zero/Few-Shot)**  
- **Models:** BERT, GPT-2  
- **Approach:** Zero-shot vs Few-shot sentiment classification  
- **Focus:** Generalization, handling nuanced/sarcastic text  

---

## Results  

### File 1 — Sentiment Analysis (Traditional ML)
| Model        | Vectorizer | Accuracy |
|--------------|------------|---------:|
| Naïve Bayes  | Count      | 91.34%   |
| Naïve Bayes  | TF-IDF     | 90.35%   |
| SVM          | Count      | 93.91%   |
| **SVM**      | **TF-IDF** | **94.22%** |
| VADER        | —          | 86.61%   |

### File 2 — Deep Learning (RNNs)
| Model | Embeddings | Accuracy |
|------|------------|---------:|
| **GRU**  | **Trainable** | **95.59%** |
| LSTM | Trainable  | 95.45%  |
| GRU  | Frozen     | lower   |
| LSTM | Frozen     | lower   |

### File 3 — Topic Modeling (Unsupervised)
- **Topic 0/1:** General function words, catch-all clusters  
- **Topic 2:** Spanish-language reviews (cultural subset)  
- **Topic 3:** Employee/service concerns (reckless, irresponsible)  
- **Clustering:** Topics 0 & 1 linked; 2 & 3 distinct → visualized via dendrograms  

### File 4 — Transformers (Zero/Few-Shot)
- **BERT:** Strong contextual sentiment classification  
- **GPT-2:** Captures nuance, less consistent for labels  
- **Zero-shot:** No labels required; broad generalization  
- **Few-shot:** Higher accuracy with curated examples, data-intensive  

---

## Key Drivers / Insights  
- **Food quality, service, and atmosphere** strongly influence sentiment polarity.  
- **SVM + TF-IDF** outperforms other traditional ML baselines.  
- **GRU with trainable embeddings** is the best-performing deep model (95.59%).  
- **Zero-shot BERT** generalizes well; **few-shot** excels with curated examples.  
- Topic modeling uncovers **linguistic diversity** (Spanish vs English) and **service concerns**, adding interpretability.  

---

## Future Work  
- Hyperparameter tuning (**SVM C & gamma; GRU hidden size & dropout; early stopping**).  
- Add SHAP/LIME explainability for top models.  
- Improve sarcasm/idiom handling in transformers.  
- Deploy as a **Streamlit app** for interactive exploration.
