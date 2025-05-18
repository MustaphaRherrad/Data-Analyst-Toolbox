**Pandas** est une bibliothèque essentielle en **Python** pour la **manipulation et l’analyse de données**. Elle permet de travailler efficacement avec des **DataFrames** et d'effectuer diverses opérations comme le **nettoyage, le filtrage, l’agrégation et la visualisation**. 🚀  

---

## ✅ **1. Installation de Pandas**  

### **🔹 Installer Pandas avec pip**
Si Pandas n’est pas installé sur ton système, tu peux l’ajouter via **pip** :  
```bash
pip install pandas
```

### **🔹 Vérifier l’installation**  
Dans Python, vérifie que Pandas est bien installé :  
```python
import pandas as pd
print(pd.__version__)  # Affiche la version installée
```

---

## 📦 **2. Chargement des données avec Pandas**  

### **🔹 Importer Pandas et charger un fichier CSV**
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

### **🔹 Créer un DataFrame à partir d’un dictionnaire Python**
```python
data = {"Nom": ["Alice", "Bob", "Charlie"], "Âge": [25, 30, 28], "Ville": ["Paris", "Lyon", "Marseille"]}
df = pd.DataFrame(data)

print(df)
```

---

## 🔍 **3. Exploration des données**  

### **🔹 Vérifier la structure du DataFrame**
```python
df.info()  # Afficher les types de données et valeurs manquantes
df.describe()  # Statistiques générales
df.shape  # Nombre de lignes et colonnes
df.columns  # Liste des colonnes
```

### **🔹 Afficher des valeurs uniques**
```python
print(df["Ville"].unique())  
```

---

## 🛠️ **4. Nettoyage et transformation des données**  

### **🔹 Gérer les valeurs manquantes**
```python
df.dropna()  # Supprime les lignes contenant des NaN
df.fillna(df["Âge"].mean(), inplace=True)  # Remplace par la moyenne
```

### **🔹 Renommer les colonnes**
```python
df.rename(columns={"Nom": "Prénom"}, inplace=True)
```

### **🔹 Supprimer des colonnes inutiles**
```python
df.drop(columns=["colonne_a_supprimer"], inplace=True)
```

---

## 📊 **5. Filtrage et sélection des données**  

### **🔹 Filtrer sur une condition**
```python
df_filtre = df[df["Âge"] > 30]  # Sélectionner les personnes de plus de 30 ans
```

### **🔹 Sélectionner des colonnes spécifiques**
```python
df_subset = df[["Nom", "Âge"]]
```

---

## 🔄 **6. Groupement et agrégation**  

### **🔹 Regrouper par catégorie et calculer des statistiques**
```python
df_grouped = df.groupby("Ville")["Âge"].mean()
print(df_grouped)
```

### **🔹 Agrégation avancée**
```python
df_grouped = df.groupby("Ville")["Âge"].agg(["mean", "sum", "count"])
print(df_grouped)
```

---

## 📈 **7. Visualisation rapide avec Pandas**  

### **🔹 Histogramme**
```python
df["Âge"].hist()
```

### **🔹 Diagramme en barres**
```python
df.groupby("Ville")["Âge"].mean().plot(kind="bar")
```

---

## 🔥 **Résumé**
| **Fonctionnalité** | **Commande** |
|----------------|------------|
| **Installation** | `pip install pandas` |
| **Chargement CSV/Excel** | `pd.read_csv("data.csv")`, `pd.read_excel("data.xlsx")` |
| **Exploration** | `df.info()`, `df.describe()`, `df.columns` |
| **Nettoyage** | `df.dropna()`, `df.fillna()`, `df.drop(columns=["nom"])` |
| **Filtrage** | `df[df["Âge"] > 30]`, `df[["Nom", "Âge"]]` |
| **Groupement** | `df.groupby("Ville")["Âge"].mean()` |
| **Visualisation** | `df["Âge"].hist()`, `df.plot(kind="bar")` |

---

Avec **Pandas**, tu peux transformer des fichiers bruts en analyses puissantes ! 
