# 🎵 LyriValence – Song Mood Prediction

## 📌 Project Overview

**LyriValence – Song Mood Prediction** is a machine learning project that predicts the **valence (positiveness/mood)** of a song using its lyrics.

Valence is represented as a continuous value between **0 and 1**:

* 🔴 **Low Valence (0–0.33):** Sad / Negative
* 🟡 **Medium Valence (0.33–0.66):** Neutral / Mixed
* 🟢 **High Valence (0.66–1):** Happy / Positive

The project uses **Natural Language Processing (NLP)** to transform song lyrics into numerical features using **TF-IDF**, followed by regression models to predict the valence score.

---

## 🎯 Objectives

* Analyze song lyrics using NLP techniques.
* Clean and preprocess textual data.
* Convert lyrics into numerical TF-IDF features.
* Train multiple machine learning regression models.
* Compare model performance using **MAE, RMSE, and R²**.
* Identify the best-performing model.
* Predict the valence of previously unseen song lyrics.
* Convert predicted valence into an interpretable mood category.

---

## 📊 Dataset

The project uses the **150K Lyrics Labeled with Spotify Valence** dataset.

**Dataset:** `labeled_lyrics_cleaned.csv`

The main fields used are:

| Column    | Description          |
| --------- | -------------------- |
| `artist`  | Artist name          |
| `song`    | Song title           |
| `lyrics`  | Song lyrics          |
| `valence` | Target valence score |

The original dataset contains approximately **158K songs**.

---

## 🛠️ Technologies Used

* 🐍 Python
* 🐼 Pandas
* 🔢 NumPy
* 📊 Matplotlib
* 📈 Seaborn
* 🧠 Scikit-learn
* 📝 NLTK
* 💾 Joblib
* ☁️ KaggleHub

---

## 🔄 Project Workflow

```text
Song Lyrics
     ↓
Data Collection
     ↓
Data Cleaning
     ↓
Missing Value & Duplicate Removal
     ↓
Text Cleaning
     ↓
Stopword Removal
     ↓
Lemmatization
     ↓
TF-IDF Feature Extraction
     ↓
Train / Test Split
     ↓
Machine Learning Models
     ↓
Model Evaluation
     ↓
Best Model Selection
     ↓
Valence Prediction
     ↓
Mood Classification
```

---

## 🧹 Data Preprocessing

The lyrics undergo several preprocessing steps:

* Removal of newline and carriage-return characters
* Conversion to lowercase
* URL removal
* Punctuation removal
* Number removal
* Extra-space removal
* Stopword removal
* Lemmatization
* Removal of extremely short lyrics

---

## 🔤 Feature Engineering

### TF-IDF

**Term Frequency–Inverse Document Frequency (TF-IDF)** is used to convert lyrics into numerical representations.

The implementation uses:

```text
max_features = 10,000
ngram_range = (1, 2)
min_df = 2
max_df = 0.95
sublinear_tf = True
```

Both unigrams and bigrams are considered so the model can learn from individual words as well as short word combinations.

---

## 🤖 Machine Learning Models

The project compares multiple regression algorithms:

### 1. Ridge Regression

Used as the primary model for high-dimensional sparse TF-IDF features.

### 2. Linear Regression

Provides a simple baseline for comparison.

### 3. Random Forest Regressor

Captures nonlinear relationships between textual features and valence.

---

## 📏 Model Evaluation

Models are evaluated using:

### MAE — Mean Absolute Error

Measures the average absolute difference between actual and predicted valence.

**Lower is better.**

### RMSE — Root Mean Squared Error

Penalizes larger prediction errors more strongly.

**Lower is better.**

### R² Score

Measures how much variation in valence is explained by the model.

**Higher is better.**

---

## 📊 Exploratory Data Analysis

The project includes visualizations for:

* Valence distribution
* Valence categories
* Lyrics length vs. valence
* Model RMSE comparison
* Model R² comparison
* Actual vs. predicted valence
* Prediction error distribution
* Words associated with higher valence
* Words associated with lower valence

---

## 🎵 Valence Prediction

The trained model accepts new song lyrics and returns a score between **0 and 1**.

Example:

```text
Input:
Song lyrics

        ↓

Predicted Valence:
0.78

        ↓

Mood:
Happy / Positive
```

### Mood Mapping

|     Valence | Mood                |
| ----------: | ------------------- |
|    `< 0.33` | 😔 Sad / Negative   |
| `0.33–0.66` | 😐 Neutral / Mixed  |
|    `> 0.66` | 😊 Happy / Positive |

---

## 💾 Generated Files

After running the project, the following files are generated:

```text
best_lyrics_valence_model.pkl
tfidf_vectorizer.pkl
model_comparison.csv
processed_lyrics_valence.csv
positive_valence_words.csv
negative_valence_words.csv
```

### Model Files

* `best_lyrics_valence_model.pkl` — trained best-performing model
* `tfidf_vectorizer.pkl` — fitted TF-IDF vectorizer

### Analysis Files

* `model_comparison.csv` — performance of all models
* `processed_lyrics_valence.csv` — processed dataset
* `positive_valence_words.csv` — words associated with higher valence
* `negative_valence_words.csv` — words associated with lower valence

---

## 📁 Project Structure

```text
LyriValence-Song-Mood-Prediction/
│
├── lyricsNLP.ipynb
│
├── labeled_lyrics_cleaned.csv
│
├── best_lyrics_valence_model.pkl
├── tfidf_vectorizer.pkl
│
├── model_comparison.csv
├── processed_lyrics_valence.csv
├── positive_valence_words.csv
└── negative_valence_words.csv
```

---

## 🚀 Key Features

* 🎵 Lyrics-based song mood prediction
* 📝 NLP text preprocessing
* 🔤 TF-IDF feature extraction
* 🤖 Multiple regression algorithms
* 📊 Comprehensive model evaluation
* 📈 EDA and visualization
* 🔎 Interpretation of influential words
* 🎯 New-song valence prediction
* 😊 Automatic mood categorization
* 💾 Trained model serialization

---

## 📌 Project Outcome

The project demonstrates how **Natural Language Processing and Machine Learning** can be used to estimate the emotional characteristics of songs from their lyrics.

Instead of simply classifying a song as *happy* or *sad*, the system predicts a **continuous valence score**, providing a more flexible representation of song mood.

---

## 🔮 Future Enhancements

* 🎧 Combine lyrics with Spotify audio features.
* 🎼 Include tempo, energy, danceability, loudness and acoustic features.
* 🧠 Experiment with transformer models such as BERT.
* 🎵 Build a multimodal lyrics + audio valence model.
* 🌐 Develop a web application for real-time prediction.
* 📱 Create an interactive song mood analysis interface.
* 📊 Add explainability using SHAP or similar techniques.

---

## 👩‍💻 Project

**LyriValence – Song Mood Prediction**

**Domain:** Machine Learning / Natural Language Processing
**Task:** Regression
**Target:** Song Valence
**Input:** Song Lyrics
**Primary Technique:** TF-IDF + Regression
