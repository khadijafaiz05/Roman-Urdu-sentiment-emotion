# Roman-Urdu-sentiment-emotion
Sentiment and emotion classification for Roman Urdu-English code-switched tweets, comparing TF-IDF classifiers, BiLSTM and fine-tuned multilingual transformers.
CodeSwitchSense: Sentiment and Emotion Detection in Roman Urdu-English Code-Switched Text

Group F26-09 · AI2002 Artificial Intelligence (BDS-5A) · FAST-NUCES Lahore Members: Eman Faisal, Mahnoor Fatima, Khadija Faiz Instructor: Hajra Waheed · Track: A (Research & Development)

Overview

Social media users in Pakistan often mix English with Urdu written in the Latin alphabet (Roman Urdu), sometimes within a single sentence, for example: "Aaj ka match bohat boring tha, totally waste of time". Roman Urdu has no standard spelling, so off-the-shelf English models handle this text poorly.

This project predicts the sentiment (positive, negative or neutral) and the emotion expressed in such tweets, and compares classical machine learning, deep learning and transformer-based models.

Objectives
Build a preprocessing pipeline for the spelling variation, noise and mixed languages of Roman Urdu-English tweets.
Train and compare TF-IDF classifiers, a BiLSTM and a fine-tuned multilingual transformer for sentiment and emotion classification.
Evaluate the models and analyse where and why they fail on code-switched text.
Dataset

Siddiqui, A. & Ali, S. A. (2023). Emotions Lexicons in Roman Urdu, along with Emotion Polarity and Mood categorization. Mendeley Data, Version 1. DOI: 10.17632/d5j9fgbdcn.1

10,000 tweets annotated for sentiment, emotion and mood
A bilingual emotion lexicon of about 14,000 entries

The data is not stored in this repository. Download it from https://data.mendeley.com/datasets/d5j9fgbdcn/1 and place the files in data/raw/.

Repository structure
├── data/
│   ├── raw/              # original dataset files (not committed)
│   └── processed/        # train / val / test CSVs (not committed)
├── notebooks/
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_classical_baselines.ipynb
│   ├── 03_bilstm.ipynb
│   └── 04_transformer.ipynb
├── src/                  # reusable code
├── results/              # tables, confusion matrices, plots
├── report/               # LaTeX report
└── proposal/             # project proposal
Pipeline
Preprocessing (01_data_preprocessing.ipynb): label cleaning, duplicate and conflict removal, language-group tagging, text cleaning (URLs, mentions, hashtags, emojis, repeated letters), Roman Urdu spelling normalisation, lexicon features, and a stratified 70/15/15 train/validation/test split.
Classical baselines: TF-IDF / n-grams with Logistic Regression, SVM and Naive Bayes.
BiLSTM: a neural sequence model.
Transformer: a fine-tuned XLM-R or mBERT.
Evaluation: accuracy, precision, recall, macro-F1 and confusion matrices on the held-out test set, plus error analysis of code-switched examples.
How to run
bash
git clone https://github.com/khadijafaiz05/Roman-Urdu-sentiment-emotion.git
cd Roman-Urdu-sentiment-emotion
pip install -r requirements.txt

Place the dataset files in data/raw/, then run the notebooks in order, starting with notebooks/01_data_preprocessing.ipynb, which creates data/processed/.

Project status
 Phase 1: Problem definition
 Phase 2: Data acquisition and preprocessing
 Phase 3: Model implementation
 Phase 4: Evaluation and comparative analysis
 Phase 5: Error analysis
 Phase 6: Final report
Results

To be added.

References
Siddiqui, A. & Ali, S. A. (2023). Dataset construction to detect human behavior with the help of emotions, sentiments and mood for Roman Urdu. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10831489/
