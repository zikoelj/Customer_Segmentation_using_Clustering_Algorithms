# 🛍️ Customer Segmentation using Clustering Algorithms

Ce projet vise à analyser et segmenter les clients d’un centre commercial en appliquant différentes techniques de **clustering non supervisé** sur le dataset `Mall_Customers.csv`.

---

## 📊 Objectif du Projet

- Nettoyer et prétraiter les données
- Créer de nouvelles variables catégorielles (`age_group`)
- Convertir les variables catégorielles (`Gender`, `age_group`) en format numérique
- Tester la distribution des variables à l’aide de tests statistiques (Agostino, Mann-Whitney U)
- Comparer les performances de **K-Means**, **GMM** et **DBSCAN** sur plusieurs variantes du dataset
- Identifier le meilleur modèle de segmentation
- Proposer des perspectives pour améliorer et déployer le projet

---

## 🗂️ Dataset

- Fichier : `Mall_Customers.csv`
- Colonnes d'origine :
  - `CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, `Spending Score (1-100)`

---

## ⚙️ Étapes de Traitement

### 1. 📦 Prétraitement

- Suppression des doublons et gestion des valeurs manquantes
- Création de la colonne catégorielle `age_group` :
  - Groupes : `Teen`, `Young Adult`, `Adult`, `Senior`
- **Encodage des variables catégorielles** (`Gender`, `age_group`) via `LabelEncoder` ou encodage one-hot selon les besoins du modèle

### 2. 🧪 Tests Statistiques

- **Test de normalité** : D’Agostino & Pearson sur des variables quantitatives
- **Comparaison de groupes** : Test de Mann-Whitney U (ex. : comparaison du `Spending Score` entre les genres)

### 3. 🧬 Création de 5 variantes du dataset (Features Sets)

Les modèles sont testés sur 5 jeux de données construits avec différentes combinaisons de caractéristiques :

| Nom du Set | Caractéristiques utilisées |
|------------|-----------------------------|
| **SET1**   | `Age`, `Gender`, `Spending Score`, `Annual Income` |
| **SET2**   | `Age`, `Spending Score`, `Annual Income` |
| **SET3**   | `age_group`, `Gender`, `Spending Score`, `Annual Income` |
| **SET4**   | `age_group`, `Spending Score`, `Annual Income` |
| **SET5**   | `Spending Score`, `Annual Income` |

---

## 🧠 Modèles de Clustering Testés

1. **K-Means**
2. **Gaussian Mixture Model (GMM)**
3. **DBSCAN**

Chaque modèle est entraîné sur les **5 variantes** du dataset.

### 🧮 Évaluation

Les performances de chaque algorithme sont comparées à l’aide de :

- **Silhouette Score**
- **Davies-Bouldin Index**

---

## ✅ Résultat

- Le modèle **K-Means** appliqué à **SET4** (`age_group` sans `Gender`) a fourni la **meilleure segmentation**.
- Il a permis d’identifier plusieurs groupes cohérents de clients (étudiants dépensiers, adultes économes, etc.).

---

## 🔭 Perspectives d’Amélioration

- **Ajouter davantage de caractéristiques** (fréquence d’achat, historique, satisfaction…)
- **Augmenter le volume de données clients**
- Appliquer des **méthodes de réduction de dimension** (PCA, t-SNE)
- Intégrer des **modèles hybrides ou hiérarchiques**
- **Déployer le projet** :
  - Créer une interface ou API pour la segmentation
  - **Héberger sur Hugging Face Spaces**, **Streamlit Cloud** ou autres plateformes de démo
  - Permettre à l’utilisateur d’**uploader ses données clients et recevoir une segmentation automatique**

---


---

## 💡 Technologies utilisées

- Python 3.10+
- Pandas, NumPy
- Scikit-learn, Scipy
- Seaborn, Matplotlib
- Jupyter Notebook

---

## 👤 Auteur

Zakariaa El Jabiry & Rania Jbili 
Master Ingénierie Logicielle & Décisionnelle – Faculté des Sciences, Rabat

---

## 📌 Licence

Ce projet est libre d'utilisation à des fins académiques ou personnelles.
