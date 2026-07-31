# 📧 Email Spam-Ham Classification using NLP

An end-to-end Natural Language Processing (NLP) project that automatically classifies incoming emails as **Spam** or **Ham (Legitimate)** using Machine Learning. The project covers the complete ML lifecycle including data preprocessing, feature engineering, model building, evaluation, prediction, and deployment with FastAPI.

---

## 📌 Project Overview

Email spam continues to be a major challenge for organizations, leading to security threats, phishing attacks, and productivity loss. This project builds a machine learning model capable of identifying spam emails from legitimate emails using Natural Language Processing techniques.

The trained model is deployed through a FastAPI REST API, making it easy to integrate with web applications or enterprise systems.

---

## 🎯 Business Problem

Organizations receive thousands of emails every day.

Manually filtering spam emails is:

- Time-consuming
- Error-prone
- Difficult to scale

This project automates spam detection by classifying each incoming email as either:

- **Ham** – Legitimate Email
- **Spam** – Unwanted or Malicious Email

---

## 📂 Dataset

The project uses a labeled Email Spam Dataset containing two columns:

| Column | Description |
|----------|-------------|
| email_text | Email content |
| label | Spam or Ham |

The dataset contains both spam and legitimate emails for supervised learning.

---

## ⚙️ Project Workflow

```
Raw Email Dataset
        │
        ▼
Data Loading
        │
        ▼
Text Preprocessing
        │
        ▼
Feature Extraction
(Count Vectorizer)
        │
        ▼
Multinomial Naive Bayes
        │
        ▼
Model Evaluation
        │
        ▼
Prediction
        │
        ▼
FastAPI Deployment
```

---

## 🧹 NLP Preprocessing

The email text is cleaned using several NLP techniques:

- Lowercase conversion
- URL removal
- Special character removal
- Stop-word removal
- Lemmatization using spaCy

This preprocessing improves the quality of the features used by the machine learning model.

---

## 🧠 Feature Engineering

The cleaned text is converted into numerical features using:

- **CountVectorizer (Bag of Words)**

Configuration:

- Maximum Features: 5000
- N-grams: (1,2)

---

## 🤖 Machine Learning Model

Algorithm used:

- **Multinomial Naive Bayes**

Reasons for choosing this model:

- Fast training
- Efficient for text classification
- Works well with Bag-of-Words features
- Strong baseline model for spam detection

---

## 📊 Model Evaluation

The trained model was evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Classification Report
- Confusion Matrix

---

## 🚀 Deployment

The trained model is deployed using **FastAPI**.

API Endpoint:

```
POST /predict
```

Example Request

```json
{
    "text": "Congratulations! You won a free iPhone."
}
```

Example Response

```json
{
    "prediction": "spam"
}
```

---

## 🗂️ Project Structure

```
Email_Spam_Detection
│
├── data
│   ├── raw
│   ├── processed
│   └── sample
│
├── models
│   ├── count_vectorizer.pkl
│   └── spam_model.pkl
│
├── notebooks
│
├── src
│   ├── api
│   ├── data
│   ├── features
│   ├── models
│   ├── quarantine
│   └── utils
│
├── main.py
├── requirements.txt
└── README.md
```

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- spaCy
- Scikit-learn
- CountVectorizer
- Multinomial Naive Bayes
- Joblib
- FastAPI
- Uvicorn

---

## ▶️ Installation

Clone the repository

```bash
git clone https://github.com/your-username/email-spam-ham-classification.git
```

Navigate to the project

```bash
cd email-spam-ham-classification
```

Create a virtual environment

```bash
python -m venv .venv
```

Activate the environment

Windows

```bash
.venv\Scripts\activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

Download the spaCy language model

```bash
python -m spacy download en_core_web_sm
```

---

## ▶️ Run the Project

Run preprocessing

```bash
python main.py
```

Train the model

```bash
python -m src.models.train
```

Run prediction

```bash
python -m src.models.predict
```

Start FastAPI

```bash
uvicorn src.api.app:app --reload
```

Open Swagger UI

```
http://127.0.0.1:8000/docs
```


---

## 👨‍💻 Author

**Pavithra G**

Aspiring Data Scientist | Machine Learning | NLP | Python