# Nettoyage_des_données.md

Le **nettoyage des données** est une étape essentielle en **Data Science** et **analyse de données**. Il permet de **supprimer les erreurs, combler les valeurs manquantes et harmoniser** les données avant toute analyse.  

---

## 📌 **1. Identifier les problèmes courants**  
Avant de nettoyer un dataset, il faut repérer **les erreurs** courantes :  
✅ **Valeurs manquantes** (`NaN`)  
✅ **Doublons**  
✅ **Données incohérentes** (âges négatifs, erreurs de saisie)  
✅ **Types de données incorrects** (texte au lieu de nombres)  

### **🔍 Vérifier la structure des données**  
```python
import pandas as pd

df = pd.read_csv("data.csv")

# Aperçu du dataset
print(df.info())  # Types de données et valeurs manquantes
print(df.describe())  # Statistiques générales
print(df.head())  # Voir les premières lignes
```

---

## 🛠️ **2. Gérer les valeurs manquantes**  

### **🔹 Supprimer les lignes/colonnes avec trop de NaN**
```python
df.dropna()  # Supprime toutes les lignes contenant des NaN
df.dropna(axis=1)  # Supprime toutes les colonnes contenant des NaN
```

### **🔹 Remplacer les valeurs manquantes par une moyenne/médiane**  
```python
df["âge"].fillna(df["âge"].mean(), inplace=True)  # Remplace par la moyenne
df["revenu"].fillna(df["revenu"].median(), inplace=True)  # Remplace par la médiane
```

---

## 🔄 **3. Supprimer les doublons**  

```python
df.drop_duplicates(inplace=True)
```

---

## 📊 **4. Corriger les incohérences**  

### **🔹 Convertir les types de données**  
Si une colonne contenant des nombres est en **format texte** :  
```python
df["revenu"] = pd.to_numeric(df["revenu"], errors="coerce")
```

### **🔹 Remplacer les erreurs typographiques**  
```python
df["ville"] = df["ville"].replace({"paris": "Paris", "lyon ": "Lyon"})
```

### **🔹 Filtrer les valeurs aberrantes**  
```python
df = df[df["âge"] > 0]  # Supprime les âges négatifs
df = df[df["revenu"] < 1000000]  # Supprime les revenus extrêmes
```

---

## 🎨 **5. Standardiser et transformer les données**  

### **🔹 Normaliser les colonnes numériques**  
```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
df[["revenu"]] = scaler.fit_transform(df[["revenu"]])
```

### **🔹 Convertir une colonne catégorielle en numérique (One-Hot Encoding)**  
```python
df = pd.get_dummies(df, columns=["profession"])
```

---

### **🔥 Résumé : Nettoyage en une seule commande**  
```python
df = df.dropna().drop_duplicates()
df["âge"] = df["âge"].fillna(df["âge"].mean())
df = df[df["âge"] > 0]
```

---

Avec ces techniques, ton dataset sera **propre et prêt pour l’analyse !**  

