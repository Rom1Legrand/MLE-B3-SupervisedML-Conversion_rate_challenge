# 📊 Prédiction des Conversions Newsletter - Projet Data Science

## 🏆 Contexte du Concours
Ce projet s'inscrit dans le cadre d'un concours interne de data science. L'objectif était de développer le meilleur modèle prédictif pour le taux de conversion d'une newsletter, évalué sur un jeu de données test invisible. Notre modèle a obtenu la 2ème place du classement ! 🥈

## 📝 Description du Projet
Ce projet vise à prédire si un utilisateur va s'abonner à la newsletter de datascienceweekly.org en se basant sur diverses caractéristiques comportementales et démographiques. L'objectif est d'optimiser le taux de conversion et de fournir des recommandations business actionnables.

## 📚 Dataset
Le dataset contient 284,580 entrées avec les variables suivantes :
- 🌍 `country` : Pays de l'utilisateur
- 👤 `age` : Âge de l'utilisateur
- 🆕 `new_user` : Si l'utilisateur est nouveau (1) ou existant (0)
- 🔍 `source` : Source d'acquisition (Direct, Ads, SEO)
- 📱 `total_pages_visited` : Nombre de pages visitées
- ✅ `converted` : Variable cible (1 si converti, 0 sinon)

## 🛠️ Méthodologie

### 1. 🔍 Analyse Exploratoire
- Analyse de la distribution des variables
- Identification des relations entre variables
- Traitement des outliers (âge > 90 ans)
- Étude du déséquilibre des classes (3.22% de conversions)

### 2. ⚙️ Préprocessing
- Standardisation des variables numériques
- Encodage one-hot des variables catégorielles
- Split train/test (85/15)

### 3. 🤖 Modélisation
Trois modèles ont été développés et comparés :
- Régression Logistique (baseline)
- Régression Logistique optimisée (GridSearchCV et Thresholds tuning)
- Random Forest

### 4. 📈 Évaluation
Métriques principales :
- F1-Score
Métriques accessoires :
- Précision
- Recall

## 🎯 Résultats Clés
Avant transmission sur le test set aveugle, le meilleur modèle (Régression Logistique optimisée) a atteint :
- F1-Score : 0.787
- Précision : 0.829
- Recall : 0.749

Les résultats du concours sont disponibles dans `src/resultats.png` ! 🏆

## 📁 Structure du Projet
├── README.md
├── conversion_rate_challenge.ipynb
├── src/
│   ├── conversion_data_train.csv
│   ├── conversion_data_test.csv
│   └── resultats.png
└── predictions/
└── predictions_logistic_regression_v2.csv

## 💡 Recommandations Business
- Optimiser l'expérience utilisateur pour augmenter les pages visitées
- Concentrer les efforts sur l'acquisition via SEO
- Adapter les stratégies selon les zones géographiques

Choix du modèle selon le contexte business :
- Si coût élevé des faux positifs → Modèle baseline (précision : 0.870)
- Si coût élevé des conversions manquées → Modèle optimisé (recall : 0.749)

## 🚀 Pistes d'Amélioration
- Test de modèles plus sophistiqués (XGBoost, LightGBM)
- Techniques de rééquilibrage des classes
- Feature engineering additionnel
- Optimisation des hyperparamètres via GridSearch
