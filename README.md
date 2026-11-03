# Détection automatique des transactions bancaires frauduleuses

Projet Machine Learning — Adem Ben Ammar, Yassin Chrif (2026)

Détection des fraudes par carte bancaire sur le jeu de données **Credit Card Fraud**
(ULB / Worldline) : 284 807 transactions, dont 492 fraudes (0,17 %).

## Contenu du dépôt

| Fichier | Description |
|---|---|
| `L01_fraude.ipynb` | Notebook principal : diagnostic, division par classe, préparation sans fuite, corrélations, choix du modèle |
| `requirements.txt` | Bibliothèques Python nécessaires |
| `rapport_fraude.pdf` | Rapport du projet |

## Contenu du notebook

1. **Exercice 1 — diagnostic** : valeurs manquantes, doublons (1 081), valeurs aberrantes (règle de Tukey), déséquilibre des classes.
2. **Exercice 1 bis — division par classe** : comparaison des transactions légitimes et des fraudes.
3. **Exercice 2 — préparation sans fuite** : suppression des doublons, séparation stratifiée 80/20, préparateur ajusté sur l'entraînement seulement.
4. **Exercice 3 — effet d'une fuite** : moyennes apprises sur l'entraînement seul ou sur toutes les données.
5. **Exercice 4 — corrélations** : une corrélation peut mentir (V17/V18 : 0,00 au global, +0,97 chez les fraudes).
6. **Exercice 5 — choix du modèle** : Régression Logistique, Random Forest et XGBoost comparés en validation croisée stratifiée à 5 plis, avec SMOTE dans le pipeline.

## Résultats principaux

| Modèle | AUPRC (validation croisée) |
|---|---|
| Régression Logistique | 0,716 ± 0,064 |
| Random Forest | 0,822 ± 0,039 |
| **XGBoost (retenu)** | **0,836 ± 0,033** |

Sur le jeu de test, XGBoost obtient une AUPRC de 0,866 : 82 fraudes détectées sur 95,
38 fausses alertes sur 56 651 transactions légitimes.

## Données

Le fichier CSV (environ 150 Mo) **n'est pas inclus** dans le dépôt : il dépasse la limite
de taille de GitHub. Téléchargez-le sur Kaggle :
<https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud> (licence ODbL), puis placez
`creditcard.csv` dans le même dossier que le notebook.

## Exécution

```bash
pip install -r requirements.txt
jupyter lab
```

Ouvrez `L01_fraude.ipynb`, puis **Kernel → Restart Kernel and Run All Cells**.
L'exercice 5 prend 5 à 10 minutes.

## Référence

A. Dal Pozzolo, O. Caelen, R. A. Johnson et G. Bontempi, « Calibrating probability with
undersampling for unbalanced classification », *IEEE SSCI*, 2015.
"# -Projet-d-tection-de-fraude-diagnostic-corr-lations-et-choix-du-mod-le-" 
