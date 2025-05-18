Les formats **XML** et **JSON** sont très utilisés en **échange de données** et en **programmation**.

---
# I. JSON_et_XML: Notions de base
---

## 📜 **Format XML (Extensible Markup Language)**  

### **🔹 Description**  
**XML** est un langage utilisé pour **structurer et stocker des données** dans un format hiérarchique. Il est souvent employé pour les **configurations, échanges de données et bases de connaissances**.  

### **📌 Caractéristiques :**  
- Basé sur une **structure hiérarchique** (comme HTML).  
- Lisible par les humains et les machines.  
- Très utilisé en **web services** et **bases de données**.  

### **📜 Exemple de fichier XML :**  
```xml
<?xml version="1.0" encoding="UTF-8"?>
<entreprise>
    <employe id="1">
        <nom>Alex</nom>
        <poste>Data Analyst</poste>
        <age>28</age>
    </employe>
    <employe id="2">
        <nom>Emma</nom>
        <poste>Développeur</poste>
        <age>30</age>
    </employe>
</entreprise>
```

### **📌 Manipulation XML en Python**  
Utilisation de **ElementTree** pour **lire** et **extraire** des informations :  
```python
import xml.etree.ElementTree as ET

# Charger le fichier XML
tree = ET.parse("data.xml")
root = tree.getroot()

# Afficher tous les noms des employés
for employe in root.findall("employe"):
    print(employe.find("nom").text)
```

---

## 📊 **Format JSON (JavaScript Object Notation)**  

### **🔹 Description**  
**JSON** est un format ultra populaire pour **échanger des données entre applications**, notamment dans les **API web** et **bases NoSQL**.  

### **📌 Caractéristiques :**  
- **Format léger** et facile à analyser.  
- Utilisé par la plupart des **langages de programmation**.  
- Compatible avec JavaScript et les bases de données comme **MongoDB**.  

### **📊 Exemple de fichier JSON :**  
```json
{
    "entreprise": {
        "employes": [
            {
                "id": 1,
                "nom": "Alex",
                "poste": "Data Analyst",
                "age": 28
            },
            {
                "id": 2,
                "nom": "Emma",
                "poste": "Développeur",
                "age": 30
            }
        ]
    }
}
```

### **📌 Manipulation JSON en Python**  
Utilisation du module **json** pour **lire** et **modifier** des données JSON :  

```python
import json

# Charger un fichier JSON
with open("data.json", "r", encoding="utf-8") as file:
    data = json.load(file)

# Afficher tous les noms des employés
for employe in data["entreprise"]["employes"]:
    print(employe["nom"])

# Ajouter un nouvel employé
nouvel_employe = {"id": 3, "nom": "Lucas", "poste": "Designer", "age": 27}
data["entreprise"]["employes"].append(nouvel_employe)

# Sauvegarder les modifications
with open("data.json", "w", encoding="utf-8") as file:
    json.dump(data, file, indent=4)
```

---

## 🔥 **XML vs JSON : Quel format choisir ?**
| **Format** | **Utilisation principale** | **Facilité de manipulation** |
|------------|---------------------------|------------------------------|
| **XML** | Échange de données complexes, documents | Plus verbeux, structuré |
| **JSON** | API Web, bases NoSQL, applications modernes | Simple, rapide, efficace |


---
# II. Des exemples en **bases de données**, **API** et **big data**
---
Voici des **exemples avancés** de manipulation des formats **XML** et **JSON** en **bases de données**, **API** et **Big Data**.   

---

## 🏦 **Stockage XML et JSON dans une base de données**  
Les bases de données modernes (SQL et NoSQL) permettent de **stocker et requêter** des données **XML** et **JSON**.

### **🔹 1. Stocker et requêter du JSON dans PostgreSQL**  
PostgreSQL offre un type de données `JSONB` permettant des recherches efficaces :  

```sql
CREATE TABLE employes (
    id SERIAL PRIMARY KEY,
    data JSONB
);

-- Insérer un employé en JSON
INSERT INTO employes (data) VALUES (
    '{"nom": "Alice", "poste": "Data Analyst", "age": 28}'
);

-- Extraire le nom depuis le JSON
SELECT data->>'nom' FROM employes WHERE data->>'poste' = 'Data Analyst';
```

---

### **🔹 2. Stocker du XML dans MySQL**  
Si une entreprise veut gérer des fichiers XML en MySQL :  

```sql
CREATE TABLE documents (
    id INT AUTO_INCREMENT PRIMARY KEY,
    contenu XML
);

-- Insérer un document XML
INSERT INTO documents (contenu) VALUES (
    '<rapport><titre>Analyse Data</titre><auteur>Emma</auteur></rapport>'
);

-- Extraire un élément spécifique
SELECT ExtractValue(contenu, '/rapport/titre') FROM documents;
```

---

## 🌍 **Consommer des API en JSON et XML**  
Les **API REST** utilisent JSON, tandis que certaines **API SOAP** utilisent XML.  

### **🔹 3. Récupérer des données JSON depuis une API**  
Exemple avec une API publique en **Python** :

```python
import requests

url = "https://api.github.com/users/MustaphaRherrad"
response = requests.get(url)

# Extraire et afficher les données JSON
data = response.json()
print(f"Nom GitHub : {data['login']}, Nombre de repos : {data['public_repos']}")
```

---

### **🔹 4. Envoyer des données XML avec une requête API SOAP**  
Exemple de requête XML avec **requests** :

```python
xml_data = """<?xml version="1.0"?>
<requete>
    <utilisateur>Mustapha</utilisateur>
    <action>ObtenirInfos</action>
</requete>
"""

response = requests.post("https://api.example.com/soap", data=xml_data, headers={"Content-Type": "application/xml"})
print(response.text)
```

---

## 🏢 **Big Data : Analyse de gros volumes de JSON/XML**  
Dans le **Big Data**, on manipule **des tonnes de fichiers JSON et XML** avec Spark et Hadoop.

### **🔹 5. Manipulation de JSON avec Apache Spark**  
Si une entreprise analyse des **données JSON massives**, elle peut utiliser **PySpark** :

```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("JSON_Processing").getOrCreate()

# Lire un fichier JSON volumineux
df = spark.read.json("big_data.json")

# Sélectionner des informations spécifiques
df.select("nom", "age").show()

# Filtrer les employés de plus de 30 ans
df.filter(df.age > 30).show()
```

---

### **🔹 6. Analyse de fichiers XML avec Hadoop**  
Si une entreprise stocke **des gigas de fichiers XML**, elle peut utiliser **Hadoop** avec Spark :

```python
from pyspark.sql.functions import col

df = spark.read.format("com.databricks.spark.xml") \
    .options(rowTag="employe") \
    .load("big_data.xml")

# Afficher les données XML
df.select("nom", "poste").show()
```

---

## **🔎 Conclusion**  
| **Utilisation** | **Technologie** | **Format recommandé** |
|----------------|---------------|----------------------|
| **Bases de données** | PostgreSQL (JSONB), MySQL (XML) | **JSON** pour requêtes rapides, **XML** pour hiérarchies complexes |
| **API** | REST (JSON), SOAP (XML) | **JSON** pour Web, **XML** pour échanges standards |
| **Big Data** | Apache Spark, Hadoop | **JSON** pour analytics, **XML** pour données réglementaires |

---

Ces outils sont essentiels pour **structurer, analyser et interagir avec des données massives**.

