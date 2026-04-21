# Unsupervised Topic Discovery and User Behavior Clustering
## in Online Mental Health Communities

Final project for Unsupervised Machine Learning — Spring 2026.

## Project Summary
Applied 7 unsupervised ML techniques to 52,484 mental health social media posts
to discover hidden topics, cluster users by linguistic behavior, and identify
co-occurring symptoms — without using any labels during modeling.

## Techniques Used
- LDA Topic Modeling (3 topics discovered)
- K-Means Clustering (2 clusters: Functional vs Distressed)
- Agglomerative (Hierarchical) Clustering
- DBSCAN (outlier/crisis post detection)
- PCA (crisis vs clinical language axis)
- Factor Analysis (5 psychological dimensions)
- Association Rule Mining / Apriori (796 rules)

## Dataset
Combined Mental Health Dataset from Kaggle.
Place `Combined Data.csv` in the `data/` folder before running.

## Reproducibility
1. Python 3.10 via Miniconda, environment: `pyass`
2. Install dependencies:
pip install pandas scikit-learn gensim nltk spacy pyLDAvis wordcloud mlxtend ipykernel seaborn matplotlib
3. Download spaCy model: `python -m spacy download en_core_web_sm`
4. Download dataset from Kaggle → place at `data/Combined Data.csv`
5. Run `notebooks/01_data_exploration.ipynb` top to bottom
6. All random seeds set to 42 throughout

## Project Structure
""
mental_health_nlp/
├── data/               # Dataset (not tracked by Git — add manually)
├── models/             # Saved models (not tracked by Git)
├── notebooks/          # Jupyter notebooks + output figures
│   └── 01_data_exploration.ipynb
└── README.md
""

## Key Findings
- All algorithms independently discovered two language groups: **Functional** vs **Distressed**
- PCA revealed a crisis-to-clinical severity axis (PC2) without any labels
- DBSCAN flagged 2,192 outlier posts including the most specific crisis language
- Strongest association rule: therapy ↔ medication (lift 3.84)
