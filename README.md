# ❓ Quora Duplicate Question Pair Detector

A machine learning project that detects whether two questions asked on Quora are semantically similar (i.e., duplicates) or not. This was a famous problem on Kaggle, and this implementation includes detailed EDA, feature engineering, and modeling pipelines.

🔗 Live App: Streamlit Demo

## 🧠 Problem Statement

Given a pair of questions from Quora, determine whether they are duplicates — i.e., essentially ask the same thing. This helps reduce redundancy and improve the quality of question-answer systems.

⸻
## 📊 Dataset
	•	📁 File: train.csv
	•	📌 404,000+ question pairs
	•	⚙️ Columns: qid1, qid2, question1, question2, is_duplicate
	•	🏷️ Target: is_duplicate → 1 if duplicate, else 0

## 🔍 Exploratory Data Analysis

Conducted in initial_EDA.ipynb:
	•	Checked for nulls and duplicate rows
	•	Calculated question repeat frequency
	•	Visualized duplicate vs. non-duplicate distributions
	•	Histogram of repeated question counts

## 🏗️ Feature Engineering

✅ Basic Features
	•	Length of questions
	•	Common words count
	•	Word overlap ratio

✅ Advanced Features (from NLP notebook)

Token Features
	•	cwc_min, cwc_max: Common word count ratio (min/max)
	•	ctc_min, ctc_max: Common token ratio
	•	csc_min, csc_max: Common stopwords ratio
	•	first_word_eq, last_word_eq: Whether first/last words match

Length-Based Features
	•	Absolute and mean lengths
	•	Difference in word counts

Fuzzy Matching
	•	Fuzz ratio, partial ratio, token sort ratio, etc. from fuzzywuzzy

## 📦 Models

Implemented in bow-with-* notebooks:
	•	Bag of Words (BOW) vectors with CountVectorizer
	•	Concatenated BOW features + engineered features
	•	Classifier: LogisticRegression and other variants tested

## 📈 Performance

You can test model accuracy and ROC-AUC via the evaluation section of the notebooks.

✅ In practice, the final model demonstrates solid performance using a mix of linguistic and semantic features — accurately distinguishing between duplicates and non-duplicates on held-out test data.

## 🌐 Web App

A simple and functional Streamlit web app built using app.py.

Features:
	•	User inputs two questions
	•	App predicts if they’re duplicates
	•	Easy-to-use interface and responsive layout
    
## 🏆 Real-World Use

This project is based on a real Kaggle competition by Quora and demonstrates end-to-end ML workflow, from EDA to production-level app deployment. Great for showcasing your skills in:
	•	NLP and text preprocessing
	•	Feature engineering
	•	Model deployment
	•	Real-world problem-solving

