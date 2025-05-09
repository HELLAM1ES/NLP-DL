# Détection de l'humour dans des textes courts (NLP & Deep Learning)

## Introduction

Ce projet vise à concevoir un système de **détection automatique de l'humour** dans des textes courts en anglais. L’humour, de par sa nature implicite, contextuelle et culturellement ancrée, constitue un véritable défi pour les modèles de traitement automatique du langage (NLP).

Notre démarche combine des approches classiques (TF-IDF + SVM) et des **modèles profonds** basés sur les Transformers (BERT, DistilBERT), avec une analyse fine des performances, des erreurs et des limites.

---

## 🗂 Structure du dépôt

```
NLP/
│
├── data/
│   ├── clean_dataset.csv
│   └── dataset.csv
│
├── vectorizers/
│   └── tfidf/
│       └── tfidf5000_vectorizer.joblib
│
├── models/
│   └── logistic_regression_tfidf.joblib
│
├── 01_EDA.ipynb              # Analyse exploratoire des données
├── 02_Preprocessing.ipynb    # Nettoyage et prétraitement textuel
├── 03_Baseline.ipynb         # Modèle baseline avec TF-IDF + SGDClassifier
├── 04_Models.ipynb           # Modèles classiques et profonds (BERT, DistilBERT)
├── 05_Analyse.ipynb          # Analyses d’erreurs, surprisal, traductions
├── requirements.txt          # Dépendances Python
```

---

## Résultats clés

### Baseline (TF-IDF + SGDClassifier)

- **Accuracy** : 86%
- **F1-score** (macro) : 0.86

### Modèles classiques (avec TF-IDF ou CountVectorizer)

| Modèle              | Vectoriseur | F1-score | Accuracy |
|---------------------|-------------|----------|----------|
| LogisticRegression  | TF-IDF      | 0.8752   | 0.8752   |
| SVM (LinearSVC)     | TF-IDF      | 0.8756   | 0.8756   |
| NaiveBayes          | Count       | 0.8708   | 0.8708   |

### BERT

- **Accuracy** : 86%
- **Recall (classe humoristique)** : 0.91

### DistilBERT (5% du dataset)

- **F1-score** : 0.9726 

---

##  Méthodologie

- Nettoyage et lemmatisation avec **spaCy**
- Vectorisation avec **TF-IDF** et **CountVectorizer**
- Modèles classiques : LogisticRegression, RandomForest, NaiveBayes, SVM
- Modèles profonds : **BERT**, **DistilBERT**
- Évaluation : Accuracy, F1-score, Matrice de confusion

---

##  Analyses avancées

- **Erreurs typiques** analysées manuellement (humour subtil, ironie, jeux de mots)
- **Surprisal linguistique** avec GPT-2 (analyse de la prévisibilité linguistique)
- **Traduction automatique** de blagues avec MarianMT
- Pistes explorées : interprétabilité (LIME, SHAP), types d’humour, apprentissage zero-shot

---

##  Pour exécuter le projet

1. Cloner le repo :
   ```bash
   git clone https://github.com/votre_utilisateur/NLP-Humour-Detection.git
   cd NLP-Humour-Detection
   ```

2. Créer un environnement :
   ```bash
   python -m venv NLP_env
   source NLP_env/bin/activate  # (ou NLP_env\Scripts\activate sous Windows)
   ```

3. Installer les dépendances :
   ```bash
   pip install -r requirements.txt
   ```

4. Lancer les notebooks dans l’ordre :
   - `01_EDA.ipynb`
   - `02_Preprocessing.ipynb`
   - `03_Baseline.ipynb`
   - `04_Models.ipynb`
   - `05_Analyse.ipynb`

---

##  Références et bibliothèques

- spaCy, scikit-learn, pandas, seaborn, matplotlib
- HuggingFace `transformers` (BERT, DistilBERT, MarianMT, GPT-2)
- ConfusionMatrixDisplay, TfidfVectorizer, CountVectorizer

---

##  Perspectives

- Interprétabilité (LIME, SHAP)
- Annotation de types d’humour (ironie, absurde, etc.)
- Apprentissage zero-shot / few-shot
- Approche multilingue ou cross-culturelle
- Modélisation multimodale (texte + image + son)

---

## 👨‍🏫 Auteur

Ce projet a été réalisé dans le cadre du cours de **Deep Learning & NLP**.

📧 Contacts : [chirine.dexposito@etu.univ-paris1.fr
hella.bouhadda@etu.univ-paris1.fr]  

---#   N L P - D L  
 