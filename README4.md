# Data Science Project 4 (Optional): NLP & Sentiment Analysis

## 📌 Overview
This project is an **optional bonus milestone** from my Data Science Internship
at **DecodeLabs** (Batch 2026), completed to add "Natural Language Processing &
Unstructured Data Handling" to my verified skill set. The goal is to build a
pipeline that reads raw, unstructured text (product/movie reviews) and predicts
whether the sentiment is Positive or Negative.

## 🎯 Objective
- Build a text pre-processing pipeline (tokenization, stop-word removal, lemmatization)
- Convert unstructured text into numerical form using TF-IDF
- Train a Naive Bayes classifier to predict review sentiment
- Correctly handle negation words (e.g., "not happy") that are often lost during
  standard text cleaning

## 📊 Dataset
This project uses the **IMDB Movie Reviews dataset** (50,000 labeled reviews,
Positive/Negative), a standard benchmark dataset for sentiment analysis tasks.

## 🛠️ Steps Performed

### 1. Text Cleaning
- Lowercased all text
- Removed HTML tags (e.g., `<br>`), punctuation, and numbers
- Removed extra whitespace

### 2. Tokenization
- Split cleaned text into individual word tokens using NLTK

### 3. Stop-Word Removal (with a Critical Fix)
- Removed common filler words (e.g., "the", "is", "a") that carry no sentiment value
- **Explicitly preserved negation words** ("not", "never", "no", etc.) in the
  stop-word list, since removing them can flip a review's true meaning
  (e.g., "not happy" incorrectly becoming "happy")

### 4. Lemmatization
- Reduced each word to its dictionary root form using NLTK's `WordNetLemmatizer`
- Used Part-of-Speech (POS) tagging to ensure accurate reduction of verbs and
  adjectives (e.g., "went" → "go", not left unchanged)

### 5. Vectorization — TF-IDF
- Converted cleaned text into numerical feature vectors using **TF-IDF**
  (Term Frequency–Inverse Document Frequency)
- Included both **unigrams and bigrams** (e.g., "good" and "not good") to
  capture negated phrases correctly
- Limited vocabulary to the top 10,000 terms to control dimensionality

### 6. Model Training — Multinomial Naive Bayes
- Trained a `MultinomialNB` classifier on the TF-IDF vectors
- Applied **Laplace Smoothing** (alpha=1.0) to prevent zero-probability errors
  on unseen words during prediction

### 7. Evaluation
- Evaluated the model on a held-out test set using Accuracy, Precision, Recall,
  F1-score, and a Confusion Matrix
- Tested the model on custom example sentences to verify correct handling of
  negations (e.g., distinguishing "not happy" from "not bad")

## 📈 Results
- Test Accuracy: **[X]%**
- Precision (Positive class): **[X]**
- Recall (Positive class): **[X]**
- [Add a note here on how the model performed on your custom negation test
  sentences from Cell 12, e.g., "Correctly classified 'not happy' as Negative
  and 'not bad' as Positive."]

## 🧰 Tools & Libraries
- Python
- Pandas, NumPy
- NLTK (tokenization, stop-words, lemmatization, POS tagging)
- Scikit-Learn (TF-IDF Vectorizer, Multinomial Naive Bayes)

## 📁 Files
- `Project_4_NLP_Sentiment_Analysis.ipynb` — main notebook with all code and outputs

## 🙋 Author
[Harshita V Kundgol]
Data Science Intern @ DecodeLabs, Batch 2026
