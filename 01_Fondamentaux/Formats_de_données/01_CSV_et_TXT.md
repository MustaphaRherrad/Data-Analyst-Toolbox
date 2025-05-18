Les formats de fichiers **TXT** et **CSV** sont très utilisés en **analyse de données**.

---
# I. Les formats txt et csv: Notions de base
---

## 📜 **Format TXT (Texte Brut)**
### **🔹 Description**  
Un fichier **TXT** contient du **texte brut**, sans mise en forme ni structure définie. Il est souvent utilisé pour stocker des données sous forme de texte simple, sans séparateur spécifique.

### **📌 Caractéristiques :**
- Contient **du texte brut** (sans styles ni polices).
- **Facile à lire et modifier** avec n’importe quel éditeur (Bloc-notes, VS Code, etc.).
- **Utilisable dans la programmation** pour stocker des logs ou des configurations.

### **Exemple de fichier `.txt` :**
```
Alice Âge : 25 ans. Elle habite à Paris
```
Ici, les données ne sont pas bien organisées, ce qui limite leur utilisation directe dans des logiciels d’analyse.

---

## 📊 **Format CSV (Comma-Separated Values)**
### **🔹 Description**  
Un fichier **CSV** est un fichier texte où les données sont **structurées sous forme de tableau** avec des séparateurs comme `,` (virgule) ou `;` (point-virgule). Il est utilisé pour **échanger et stocker des données tabulaires**.

### **📌 Caractéristiques :**
- Les valeurs sont **séparées par des virgules (`,`), des points-virgules (`;`) ou des tabulations (`\t`).
- **Facilement importable** dans Excel, Pandas (Python), SQL, etc.
- **Idéal pour les bases de données et les analyses**.

### **Exemple de fichier `.csv` :**
```
Nom,Âge,Ville
Alice,25,Paris
Bob,30,Lyon
Charlie,28,Marseille
```
Chaque ligne représente une **entrée**, et chaque valeur est **séparée** par une virgule. Ce format est idéal pour **l’analyse et le traitement de données**.

---

## 🔥 **Quand utiliser TXT ou CSV ?**
| **Format** | **Utilisation principale** |
|------------|---------------------------|
| **TXT** | Stockage de texte brut, logs, documents |
| **CSV** | Structuration de données, bases de données, analyses |

Si tu veux manipuler des fichiers CSV en **Python**, tu peux utiliser **Pandas** :

```python
import pandas as pd
df = pd.read_csv("fichier.csv")
print(df.head())
```

---
# II- Manipuler les fichiers txt et csv avec Python
---

Voici comment **manipuler** des fichiers **TXT** et **CSV** en **Python** avec quelques opérations courantes.  

---

## 🔹 **Manipulation des fichiers TXT en Python**
Les fichiers **TXT** sont simples à lire et à écrire. Voici comment **ouvrir, lire et écrire** dans un fichier `.txt` :  

### **📌 Lecture d’un fichier TXT**
```python
# Ouvrir et lire un fichier texte
with open("fichier.txt", "r", encoding="utf-8") as file:
    contenu = file.read()
print(contenu)
```

### **📌 Écriture dans un fichier TXT**
```python
# Écrire dans un fichier texte
with open("fichier.txt", "w", encoding="utf-8") as file:
    file.write("Hello, voici du texte stocké dans un fichier !")
```

---

## 📊 **Manipulation des fichiers CSV en Python**
Le format **CSV** est très utilisé en **data science**. La librairie **Pandas** facilite sa manipulation.  

### **📌 Lecture d’un fichier CSV**
```python
import pandas as pd

# Lire un fichier CSV
df = pd.read_csv("mon-fichier.csv") #pense à ajouter le sepateur la cas échéant
print(df.head())  # Affiche les 5 premières lignes
```

### **📌 Écriture dans un fichier CSV**
```python
# Créer un DataFrame et l'enregistrer en CSV
data = {"Nom": ["Alice", "Bob", "Charlie"], "Âge": [25, 30, 28], "Ville": ["Paris", "Lyon", "Marseille"]}
df = pd.DataFrame(data)

df.to_csv("nouveau_fichier.csv", index=False)  # Sauvegarde sans l’index
```

### **📌 Filtrer les données d’un CSV**
```python
# Sélectionner uniquement les personnes âgées de plus de 25 ans
df_filtre = df[df["Âge"] > 25]
print(df_filtre)
```

---

## 🔥 **Quel format choisir pour Python ?**
| **Format** | **Librairie recommandée** | **Usage principal** |
|------------|---------------------------|----------------------|
| **TXT** | `open()` | Stockage simple de texte, logs |
| **CSV** | `pandas` | Analyse et manipulation de données tabulaires |

---
# III. Des exemples plus avancés
---

 Voici **des exemples plus avancés** de manipulation de fichiers **TXT** et **CSV** en **Python**, incluant le nettoyage des données, l'analyse avancée et l'intégration avec des bases de données. 🚀  

---

## 📜 **Manipulation avancée des fichiers TXT**  
### **🔹 1. Suppression des lignes vides et nettoyage du texte**  
Si un fichier `.txt` contient des lignes vides ou des espaces inutiles, voici comment le nettoyer :  

```python
with open("texte_brut.txt", "r", encoding="utf-8") as file:
    lignes = file.readlines()

# Supprimer les lignes vides et nettoyer les espaces inutiles
lignes_nettoyees = [ligne.strip() for ligne in lignes if ligne.strip()]

with open("texte_nettoye.txt", "w", encoding="utf-8") as file:
    file.writelines("\n".join(lignes_nettoyees))

print("Nettoyage terminé 🚀")
```

### **🔹 2. Extraction d’informations spécifiques avec des expressions régulières**  
Si tu veux extraire **des numéros de téléphone** d’un fichier `.txt`, voici comment faire avec **Regex** :  

```python
import re

with open("contacts.txt", "r", encoding="utf-8") as file:
    contenu = file.read()

# Trouver tous les numéros de téléphone (format simple : 06 XX XX XX XX)
pattern = r"\b06\d{8}\b"
numeros = re.findall(pattern, contenu)

print("Numéros trouvés :", numeros)
```

---

## 📊 **Manipulation avancée des fichiers CSV**  
### **🔹 1. Fusion de plusieurs fichiers CSV**  
Si tu veux **combiner** plusieurs fichiers CSV en un seul DataFrame :  

```python
import pandas as pd
import glob

# Liste de tous les fichiers CSV dans un dossier
csv_files = glob.glob("data/*.csv")

# Fusionner les fichiers en un seul DataFrame
df_total = pd.concat((pd.read_csv(file) for file in csv_files), ignore_index=True)

# Sauvegarde du fichier final
df_total.to_csv("fusion_data.csv", index=False)
print("Fusion terminée ✅")
```

### **🔹 2. Nettoyage des données et gestion des valeurs manquantes**  
Si ton fichier CSV contient des **valeurs manquantes**, voici comment les gérer :  

```python
df = pd.read_csv("data.csv")

# Remplacer les valeurs manquantes par "Non renseigné"
df.fillna("Non renseigné", inplace=True)

# Supprimer les lignes où toutes les valeurs sont manquantes
df.dropna(how="all", inplace=True)

# Sauvegarde du fichier nettoyé
df.to_csv("data_nettoye.csv", index=False)
print("Nettoyage terminé 🔥")
```

### **🔹 3. Filtrage avancé et statistiques sur les données**  
Si tu veux analyser les **ventes de produits**, voici comment filtrer et obtenir des statistiques :  

```python
df = pd.read_csv("ventes.csv")

# Filtrer les ventes au-dessus de 1000€
df_haut_ventes = df[df["Montant"] > 1000]

# Calculer les statistiques
print("Statistiques des ventes :")
print(df.describe())

# Exporter les données filtrées
df_haut_ventes.to_csv("ventes_filtrees.csv", index=False)
print("Export terminé 🎯")
```

---

## 🏦 **Intégration des fichiers CSV dans une base de données SQLite**  
Si tu veux stocker tes données CSV dans une **base de données SQLite**, voici comment faire :  

```python
import sqlite3
import pandas as pd

# Connexion à la base SQLite
conn = sqlite3.connect("data.db")
cursor = conn.cursor()

# Création d'une table
cursor.execute("""
    CREATE TABLE IF NOT EXISTS ventes (
        id INTEGER PRIMARY KEY,
        produit TEXT,
        montant REAL,
        date TEXT
    )
""")

# Chargement des données CSV et insertion en base
df = pd.read_csv("ventes.csv")
df.to_sql("ventes", conn, if_exists="replace", index=False)

print("Données enregistrées en base ✅")

# Vérification des données
result = cursor.execute("SELECT * FROM ventes LIMIT 5").fetchall()
print(result)

# Fermeture de la connexion
conn.close()
```

---

Ces manipulations avancées **optimisent** le traitement de **TXT et CSV** et permettent une meilleure **analyse** des données ! 