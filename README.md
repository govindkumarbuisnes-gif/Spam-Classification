<div align="center">

# 📩 Spam Classification using Machine Learning

### Detect spam SMS messages instantly with NLP + Naive Bayes

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikitlearn&logoColor=white)
![NLTK](https://img.shields.io/badge/NLTK-NLP-green)
![Gradio](https://img.shields.io/badge/Gradio-Web%20UI-ff7c00)
![Accuracy](https://img.shields.io/badge/Accuracy-95.94%25-brightgreen)
![Status](https://img.shields.io/badge/Status-Completed-success)

</div>

---

## 📌 Overview

This project classifies SMS messages as **Spam** or **Ham (not spam)** using Natural Language Processing and a Machine Learning model. Raw text is cleaned and normalized, converted into TF-IDF features, and classified with a **Multinomial Naive Bayes** model. A **Gradio web app** lets you test any message live and see the confidence scores.

## ✨ Features

- 🧹 Complete text preprocessing pipeline (lowercasing, tokenization, stopword removal, stemming)
- 📊 Exploratory Data Analysis with class distribution and word clouds
- 🔢 TF-IDF feature extraction
- 🤖 Multinomial Naive Bayes classifier with **95.94% test accuracy**
- 🎯 Probability output for both Spam and Ham
- 🌐 Interactive Gradio interface for real-time predictions

## 📂 Dataset

- **Source:** SMS Spam Collection dataset (`spam.csv`)
- **Original size:** 5,572 messages
- **After removing 403 duplicates:** 5,169 messages
- **Labels:** `ham` (0) and `spam` (1)
- The dataset is **imbalanced**: ham messages far outnumber spam.

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Data handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn, WordCloud |
| NLP | NLTK (Punkt tokenizer, Stopwords, Porter Stemmer) |
| ML | scikit-learn (CountVectorizer, TfidfTransformer, MultinomialNB) |
| Deployment / UI | Gradio |

## 🔄 Project Workflow

```
Raw SMS Data
    ↓
Data Cleaning (drop extra columns, rename, remove duplicates)
    ↓
Label Encoding (ham → 0, spam → 1)
    ↓
EDA (class distribution, word counts, word clouds)
    ↓
Text Preprocessing (lowercase → tokenize → remove stopwords → stem)
    ↓
Feature Extraction (CountVectorizer → TF-IDF)
    ↓
Train / Test Split (80% / 20%)
    ↓
Multinomial Naive Bayes
    ↓
Evaluation + Gradio Web App
```

## 🧪 Text Preprocessing Example

```python
transform_text("did you like presentation, @+ of machine learning ??")
# Output: 'like present machin learn'
```

## 📈 Results

| Metric | Value |
|---|---|
| Model | Multinomial Naive Bayes |
| Vectorization | CountVectorizer + TF-IDF |
| Train / Test split | 80% / 20% (`random_state=2`) |
| **Test Accuracy** | **95.94%** |

### 🔍 Sample Predictions

| Message | Ham | Spam |
|---|---|---|
| "Hey, are we meeting tomorrow for the project discussion?" | 0.99 | 0.01 |
| "click on this link to win cash prize worth 10 lakh" | 0.32 | 0.68 |

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/govindkumarbuisnes-gif/spam-classifier.git
cd spam-classifier
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn nltk scikit-learn wordcloud gradio
```

### 3. Download NLTK data

```python
import nltk
nltk.download("punkt")
nltk.download("punkt_tab")
nltk.download("stopwords")
```

### 4. Run the notebook

Open `SpamClassification.ipynb` in **Jupyter Notebook** or **Google Colab**, make sure `spam.csv` is in the same folder, and run all cells. The last cell launches the Gradio app.

## 💻 Usage

```python
predict_spam_probability("Congratulations! You have won a free ticket. Call now!")
# {'Ham Probability': ..., 'Spam Probability': ...}
```

## 📁 Project Structure

```
spam-classifier/
├── SpamClassification.ipynb   # Main notebook
├── spam.csv                   # Dataset
└── README.md                  # Documentation
```

## ⚠️ Limitations

- Trained on an English SMS dataset from the past, so it may not catch modern spam, Hinglish messages or WhatsApp-style scams.
- Only accuracy is reported. Because the data is imbalanced, precision, recall and F1-score for the spam class are important too.
- Short, borderline messages can get uncertain scores (e.g. 0.68 spam probability above).

## 🔮 Future Improvements

- [ ] Add precision, recall, F1-score and a confusion matrix
- [ ] Compare with other models (SVM, Random Forest, Logistic Regression)
- [ ] Add Hindi / Hinglish spam support
- [ ] Deploy permanently on Hugging Face Spaces / Streamlit
- [ ] Save the model with `pickle` / `joblib` so it doesn't need retraining

## 👨‍💻 Author

**Govind Kumar**
B.Tech (AI & ML), Swami Vivekanand Subharti University, Meerut

- 📧 Email: [govindkumarbuisnes@gmail.com](mailto:govindkumarbuisnes@gmail.com)
- 🐙 GitHub: [@govindkumarbuisnes-gif](https://github.com/govindkumarbuisnes-gif)

---

<div align="center">

⭐ If you found this project useful, please give it a star!

</div>
