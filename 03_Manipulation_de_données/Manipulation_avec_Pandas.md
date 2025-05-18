**Pandas** est une bibliothèque incontournable pour **manipuler, nettoyer et analyser des données** en Python.  

---

## 📊 **1. Chargement et affichage des données**  

### **🔹 Charger un fichier CSV**  
```python
import pandas as pd

# Charger un fichier CSV
df = pd.read_csv("data.csv")

# Afficher les premières lignes
print(df.head())
```

### **🔹 Charger un fichier Excel**  
```python
df = pd.read_excel("data.xlsx")
```

---

## 📌 **2. Exploration des données**  

### **🔹 Vérifier la structure du DataFrame**
```python
df.info()  # Afficher les types de données et valeurs manquantes
df.describe()  # Statistiques générales
df.shape  # Nombre de lignes et colonnes
df.columns  # Liste des colonnes
```

### **🔹 Afficher des valeurs uniques**
```python
print(df["colonne"].unique())  
```

---

## 🛠️ **3. Nettoyage des données**  

### **🔹 Gérer les valeurs manquantes**
```python
df.dropna()  # Supprimer les lignes avec NaN
df.fillna(0)  # Remplacer les NaN par 0
```

### **🔹 Renommer les colonnes**
```python
df.rename(columns={"ancienne_colonne": "nouvelle_colonne"}, inplace=True)
```

### **🔹 Supprimer des colonnes inutiles**
```python
df.drop(columns=["colonne_a_supprimer"], inplace=True)
```

---

## 📈 **4. Filtrage et sélection des données**  

### **🔹 Filtrer sur une condition**
```python
df_filtre = df[df["âge"] > 30]  # Sélectionner les personnes de plus de 30 ans
```

### **🔹 Sélectionner des colonnes spécifiques**
```python
df_subset = df[["nom", "âge"]]
```

---

## 🎨 **5. Ajout et transformation des colonnes**  

### **🔹 Ajouter une colonne calculée**
```python
df["revenu_annuel"] = df["revenu_mensuel"] * 12
```

### **🔹 Appliquer une fonction sur une colonne**
```python
df["nom_majuscule"] = df["nom"].apply(lambda x: x.upper())
```

---

## 🔄 **6. Groupement et agrégation**  

### **🔹 Groupement par catégorie**
```python
df_group = df.groupby("ville")["revenu"].mean()
print(df_group)
```

### **🔹 Comptage des valeurs**
```python
df["profession"].value_counts()
```

---

## 📊 **7. Visualisation rapide avec Pandas**  

### **🔹 Histogramme**
```python
df["âge"].hist()
```

### **🔹 Diagramme en barres**
```python
df.groupby("profession")["revenu"].mean().plot(kind="bar")
```

---

**Avec Pandas, tu peux transformer des fichiers bruts en analyses puissantes !**  

