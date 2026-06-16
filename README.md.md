# 🩺 Détection précoce du diabète — Machine Learning

Pipeline de **classification supervisée** pour prédire le risque de diabète d'un patient à partir de mesures médicales simples (glycémie, IMC, âge, tension…), comme outil d'**aide au dépistage**.

> Projet académique — Licence Sciences des Données, Université Chouaïb Doukkali (El Jadida).

## 🔧 Technologies
`Python` · `scikit-learn` · `pandas` · `numpy` · `matplotlib` · `seaborn`

## 📊 Données
- **Jeu de données :** Pima Indians Diabetes (768 patientes, 8 variables médicales)
- **Cible :** `Outcome` — diabétique (1) / non diabétique (0)

## ⚙️ Démarche
1. **Exploration (EDA)** — distributions, déséquilibre des classes (~35 % de diabétiques), corrélations
2. **Prétraitement** — détection des **zéros biologiquement impossibles** (glycémie, IMC…) traités comme valeurs manquantes, imputation par la **médiane**
3. **Normalisation** (`StandardScaler`) + découpage **80 / 20** stratifié
4. **Modélisation** — comparaison de **5 modèles**
5. **Évaluation** — accuracy, précision, rappel, F1, ROC-AUC + **validation croisée 5-fold**
6. **Interprétation** — importance des variables (facteurs de risque)

## 🏆 Résultats

| Modèle | Accuracy | F1 | ROC-AUC |
|---|:---:|:---:|:---:|
| Arbre de décision | **0.76** | **0.68** | 0.76 |
| Forêt aléatoire | 0.74 | 0.60 | **0.82** |
| SVM | 0.74 | 0.60 | 0.80 |
| KNN | 0.73 | 0.60 | 0.79 |
| Régression logistique | 0.71 | 0.55 | 0.81 |

**Facteurs de risque les plus prédictifs :** glycémie (Glucose), IMC (BMI) et âge — cohérent avec la littérature médicale.

## ▶️ Lancer le projet
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
jupyter notebook Projet_Detection_Diabete.ipynb
```

## ⚠️ Avertissement
Outil pédagogique d'aide à la décision — **ne remplace pas** un diagnostic médical réalisé par un professionnel de santé.
