
# Project_Phase3

## Objectif du projet
Ce projet a été réalisé dans le cadre du cours de **Data Science & Intelligence Artificielle** (enseignant : *Wedter Jerome*).  
Il consiste à développer un modèle de **classification supervisée** afin de prédire le **désabonnement (churn)** des clients de **SyriaTel**.  
L’objectif est d’identifier les clients à risque et de proposer des stratégies de rétention adaptées pour améliorer la fidélisation.  

##  Contenu du dépôt
- `Project_Phase3.ipynb` → Notebook principal avec le code, l’analyse et les résultats.  
- `data/bigml_59c28831336c6604c800002a.csv` → Jeu de données client (3333 enregistrements, 21 variables).  
- `requirements.txt` → Bibliothèques Python nécessaires.  

##  Étapes principales
1. **Chargement et préparation des données**
   - Nettoyage des colonnes, conversion de la variable cible `churn` en numérique.  
   - Encodage *One-Hot* des variables catégorielles.  
   - Standardisation des variables numériques.  

2. **Modélisation**
   - **Régression Logistique (baseline)** : modèle simple et interprétable, Accuracy ≈ 86% mais faible recall sur les clients churn.  
   - **Régression Logistique optimisée (GridSearchCV)** : réglage d’hyperparamètres, peu d’amélioration sur le recall.  
   - **Random Forest (modèle final)** : meilleur compromis avec ROC-AUC = 0.847 et Recall = 0.600, ce qui permet d’identifier davantage de clients à risque.  

3. **Évaluation des modèles**
   - Comparaison via Accuracy, ROC-AUC, Recall (classe churn) et F1-score.  
   - Visualisations : matrices de confusion et courbes ROC.  
   - Importance des variables pour mieux comprendre les facteurs influençant le churn.  

##  Résultats principaux
- Logistic Regression Baseline → Accuracy: 0.862 | ROC-AUC: 0.808 | Recall: 0.247 | F1: 0.343  
- Logistic Regression Optimisée → Accuracy: 0.861 | ROC-AUC: 0.808 | Recall: 0.247 | F1: 0.340  
- Random Forest (final) → Accuracy: 0.861 | ROC-AUC: 0.847 | Recall: 0.600 | F1: 0.556  


**Random Forest** est retenu comme modèle final grâce à sa meilleure capacité à détecter les clients à risque.  

## 💡 Implications métier
- Un **recall plus élevé** permet d’identifier davantage de clients susceptibles de se désabonner.  
- Cela aide la direction marketing à lancer des **actions de rétention ciblées** (offres personnalisées, appels sortants, suivi du service client).  
- Les variables clés détectées par le modèle :  
  - Nombre d’appels au service client  
  - Plan international  
  - Minutes de communication (day/evening/night)  

## 🚀 Prochaines étapes
- Approfondir l’optimisation d’hyperparamètres (Random Forest, Gradient Boosting, XGBoost).  
- Tester le rééquilibrage des classes (ex. SMOTE).  
- Ajuster les seuils de classification pour optimiser le compromis **precision vs recall**.  

## 👨‍🎓 Auteur
- **Carlos Yfrazin**  
Étudiant en **Data Science & AI**
