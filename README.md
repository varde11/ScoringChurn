# Prédiction du churn client dans le secteur des télécommunications

---

## Introduction

Chaque année, les entreprises télécoms perdent des millions à cause du départ inattendu de leurs clients. Selon *Harvard Business Review*, acquérir un nouveau client coûte entre **5 à 25 fois plus cher** que de conserver un client existant. Dans ce contexte, anticiper le churn est devenu une priorité stratégique pour les entreprises du secteur.

> **Objectif :**  
> Développer un modèle de machine learning capable d’identifier les clients les plus susceptibles de résilier leur contrat, afin de permettre aux entreprises de mettre en place des actions préventives.

---

## Contexte

Dans un marché des télécommunications hautement concurrentiel, **51 % des consommateurs français** envisagent de changer de fournisseur mobile, un taux parmi les plus élevés en Europe. Cette instabilité représente un défi majeur pour les opérateurs, car la perte de clients impacte directement leur chiffre d'affaires et leur rentabilité.  
**Source :** [e-relation-client](https://www.e-relation-client.com/taux-churn-relation-client/)

---

## Problème

**Comment anticiper efficacement les départs de clients** afin de mettre en place des actions de fidélisation ciblées et réduire le taux d'attrition ?

---

## Solution Apportée

Ce projet propose un modèle de machine learning capable d'identifier les clients les plus susceptibles de résilier leur contrat. En s'appuyant sur des données clients historiques, le modèle permet de prédire le churn et d'aider les entreprises à élaborer des stratégies de rétention efficaces.

---

## Données Utilisées

Le projet s'appuie sur le jeu de données public **Telco Customer Churn** accessible sur Kaggle, qui contient des informations sur les clients d'une entreprise de télécommunications, telles que :
- **Données du client :** sexe, statut, personnes à charge
- **Informations sur les services souscrits :** téléphonie, internet, streaming
- **Détails contractuels :** durée du contrat, mode de paiement
- **Historique de facturation :** montant mensuel, total payé
- **Statut de résiliation :** churn ou non

---

## Prétraitement des Données

Les étapes de prétraitement incluent :
- Gestion des valeurs manquantes et des données incohérentes
- Encodage des variables catégorielles
- Normalisation des variables numériques
- Création de nouvelles variables pertinentes

---

## Modélisation

Plusieurs modèles de machine learning ont été testés pour prédire le churn :
- **KNeighborsClassifier**
- **Random Forest Classifier**
- **SVM**

Le modèle final a été sélectionné en fonction de ses performances en termes de précision, rappel et F1-score.

### Approche Modulaire

- **Deux modèles distincts :**
  - **Modèle "Recall" :** Maximisation du rappel pour détecter un maximum de clients à risque (classe 1)
  - **Modèle "Précision" :** Équilibre global sur l’ensemble des clients
- **Recherche d’hyperparamètres :**  
  Utilisation de RandomizedSearchCV et GridSearchCV pour améliorer les performances sans surapprentissage.

---

## Résultats

### Modèle 1 – Optimisé pour la détection des clients à risque

| Objectif principal           | Recall (classe 1) | Accuracy |
|------------------------------|-------------------|----------|
| Détection client à risque    | 75 %              | 76 %     |

### Modèle 2 – Optimisé pour une bonne performance globale

| Objectif principal           | Precision (classe 1) | Accuracy |
|------------------------------|----------------------|----------|
| Bonne performance globale    | 70 %                 | 80 %     |

---

## Technologies Utilisées

- **Python** (pandas, scikit-learn, seaborn, matplotlib)
- **Jupyter Notebook**
- **GitHub**

---

## Conclusion

Ce projet démontre l’utilité concrète du machine learning dans la lutte contre le churn client. Grâce à l’analyse des données clients et à un modèle robuste, les entreprises peuvent anticiper les départs et agir de manière proactive pour améliorer la rétention. En exploitant les bons signaux, il devient possible d’économiser des sommes significatives tout en renforçant la satisfaction client.

---

## Perspectives d'Amélioration

- **Enrichissement des données :** Intégrer des données issues de tickets de support, d'avis clients ou des logs d’utilisation des services.
- **Analyse temporelle :** Prendre en compte l’évolution du comportement des clients dans le temps.
- **Déploiement en production :** Créer une API ou une interface pour intégrer la prédiction au système d’information de l’entreprise afin d’analyser chaque client.
- **Stratégies de rétention :** Lier les scores de churn à des campagnes marketing ou à des offres personnalisées.

---

## Point de Vue Personnel

Ce projet aborde un enjeu crucial pour le secteur des télécommunications en anticipant le churn, qui représente un coût élevé pour les entreprises. L'approche multitâche, avec deux modèles mettant respectivement l'accent sur le rappel et sur la précision, illustre une compréhension fine des compromis entre ces métriques. La diversité des techniques de prétraitement, la sélection rigoureuse des hyperparamètres et l'évaluation complète à l'aide de multiples métriques témoignent d'une démarche réfléchie et pragmatique. Les perspectives d'amélioration offrent des pistes intéressantes pour rendre le modèle encore plus pertinent et opérationnel dans un environnement réel, soulignant ainsi la valeur ajoutée du machine learning dans la fidélisation client.

