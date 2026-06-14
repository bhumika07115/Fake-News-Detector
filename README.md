# 🗞️ The Truth Press — Fake News Detector

> An automated fake news detection system built with Machine Learning and Natural Language Processing, deployed as a newspaper-inspired web application.

---

## 📌 Project Overview

This project was developed as part of the **AI for Society** course at **Fontys University of Applied Sciences**. The goal was to build a machine learning model that can automatically classify news articles as **Real** or **Fake** based on the language and content of the text.

The final model uses **Multinomial Naive Bayes** combined with **TF-IDF vectorization**, trained on the ISOT Fake News Dataset. The model is deployed through an interactive web application called **The Truth Press**, built using Streamlit.

---

## 📁 Project Structure

```
fake-news-detector/
│
├── True.csv              # Real news articles (from Kaggle)
├── Fake.csv              # Fake news articles (from Kaggle)
│
├── train_nb.py           # Training script — Multinomial Naive Bayes (final model)
├── train_lr.py           # Training script — Logistic Regression (baseline model)
├── app.py                # Streamlit web application
│
├── model.pkl             # Saved trained model (generated after training)
│
└── README.md             # Project documentation
```

---

## 🗂️ Dataset

- **Name:** Fake and Real News Dataset
- **Source:** [Kaggle — Clément Bisaillon](https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset)
- **License:** Open Database License (ODbL)
- **Size:** ~44,900 articles (21,417 real + 23,481 fake)
- **Columns:** title, text, subject, date

---

## ⚙️ Installation

### 1. Clone the repository or download the project files

### 2. Install required libraries

```bash
pip install streamlit scikit-learn pandas plotly
```

### 3. Download the dataset

Download `True.csv` and `Fake.csv` from [Kaggle](https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset) and place them in the same folder as the project files.

---

## 🚀 How to Run

### Step 1 — Train the model

```bash
python train_nb.py
```

This will train the Multinomial Naive Bayes model and save it as `model.pkl` in the same folder.

### Step 2 — Launch the web application

```bash
streamlit run app.py
```

Then open your browser and go to:

```
http://localhost:8501
```

---

## 🤖 Models

| Model | Accuracy | Notes |
|---|---|---|
| Logistic Regression | 99.45% | Higher accuracy on test set but less reliable on real world articles |
| Multinomial Naive Bayes | 96.60% | Selected as final model — generalises better to unseen articles |

---

## 🌐 Web Application

The web application is styled as a newspaper front page called **The Truth Press**. Features include:

- Paste any news headline or full article text
- Instant Real or Fake verdict with colour coded banner
- Probability bar chart showing model confidence
- Editor's note when only a short headline is entered
- Powered by Multinomial Naive Bayes

---

## 📊 Results

**Logistic Regression**
- Test Accuracy: 99.45%
- Precision: 0.99 / Recall: 0.99 / F1: 0.99

**Multinomial Naive Bayes**
- Test Accuracy: 96.60%
- Precision: 0.97 / Recall: 0.97 / F1: 0.97

---

## ⚠️ Limitations

- Only works on English language articles
- Trained on data from 2015–2018, may not perform well on recent news
- All real news comes from Reuters, which may introduce source bias
- Focused mainly on US political news

---

## 🧠 Technologies Used

| Library | Purpose |
|---|---|
| `scikit-learn` | Machine learning models and TF-IDF vectorization |
| `streamlit` | Web application framework |
| `plotly` | Interactive probability bar chart |
| `pandas` | Data loading and preprocessing |
| `pickle` | Saving and loading the trained model |

---

## 📜 References

- Bisaillon, C. (2020). Fake and Real News Dataset. Kaggle. https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset
- Pedregosa et al. (2011). Scikit-learn: Machine Learning in Python. Journal of Machine Learning Research, 12, 2825–2830.
- Streamlit Inc. (2023). Streamlit. https://streamlit.io
- Shu, K. et al. (2017). Fake News Detection on Social Media: A Data Mining Perspective. ACM SIGKDD Explorations Newsletter.

---

## 👩‍💻 Author

**Bhumika**
AI for Society — Fontys University of Applied Sciences
June 2026
