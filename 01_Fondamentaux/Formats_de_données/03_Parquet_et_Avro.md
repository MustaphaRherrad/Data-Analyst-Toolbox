Les formats **Parquet** et **Avro** sont largement utilisés en **Big Data** et en **stockage optimisé**.  

---

## 📦 **Format Parquet**  

### **🔹 Description**  
**Parquet** est un format de fichier **colonnaire**, conçu pour optimiser les performances lors de la lecture de données volumineuses. Il est particulièrement utilisé dans les **architectures Big Data** avec **Apache Spark, Hive et Hadoop**.  

### **📌 Caractéristiques**  
✔️ **Stockage colonnaire** → Permet des requêtes rapides sur certaines colonnes sans charger tout le fichier.  
✔️ **Compression efficace** → Utilise des algorithmes comme Snappy, Gzip ou LZO pour réduire l’espace de stockage.  
✔️ **Interopérabilité** → Compatible avec de nombreux outils **Big Data**.  
✔️ **Adapté aux bases de données distribuées** → Accélère les traitements en environnement distribué.  

### **📜 Exemple d'utilisation en Python avec Pandas**  
```python
import pandas as pd

# Création d’un DataFrame
data = {"Nom": ["Alice", "Bob", "Charlie"], "Âge": [25, 30, 28], "Ville": ["Paris", "Lyon", "Marseille"]}
df = pd.DataFrame(data)

# Enregistrer au format Parquet
df.to_parquet("data.parquet", engine="pyarrow", compression="snappy")

# Charger un fichier Parquet
df_parquet = pd.read_parquet("data.parquet")
print(df_parquet)
```

### **📌 Utilisation avec PySpark**  
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("ParquetExample").getOrCreate()

# Lire un fichier Parquet
df = spark.read.parquet("data.parquet")
df.show()

# Écrire un DataFrame en Parquet
df.write.parquet("output.parquet")
```

---

## 🏗️ **Format Avro**  

### **🔹 Description**  
**Avro** est un format **binaire** utilisé pour le **stockage et le transfert de données**. Contrairement à **Parquet**, il stocke les données **en ligne** (row-based), ce qui le rend plus adapté aux **transactions rapides** et à l’envoi de **données sérialisées**.  

### **📌 Caractéristiques**  
✔️ **Format binaire compact** → Réduit la taille des fichiers.  
✔️ **Inclut le schéma** → Permet une validation stricte des données.  
✔️ **Optimisé pour la sérialisation/désérialisation** → Idéal pour **Kafka et le streaming**.  
✔️ **Compatible avec Java, Python et Hadoop** → S’intègre bien aux systèmes distribués.  

### **📜 Exemple d'utilisation en Python avec Fastavro**  
```python
import fastavro
import json

# Définir un schéma Avro
schema = {
    "type": "record",
    "name": "Employe",
    "fields": [
        {"name": "nom", "type": "string"},
        {"name": "age", "type": "int"},
        {"name": "ville", "type": "string"}
    ]
}

# Données à enregistrer
data = [{"nom": "Alice", "age": 25, "ville": "Paris"}, {"nom": "Bob", "age": 30, "ville": "Lyon"}]

# Enregistrer au format Avro
with open("data.avro", "wb") as out_file:
    fastavro.writer(out_file, schema, data)

# Lire un fichier Avro
with open("data.avro", "rb") as in_file:
    reader = fastavro.reader(in_file)
    for record in reader:
        print(record)
```

---

## 🔥 **Comparaison : Parquet vs Avro**
| **Format**  | **Stockage** | **Utilisation principale** | **Avantages** |
|-------------|-------------|----------------------------|---------------|
| **Parquet** | Colonnaire  | Analytics, Big Data       | Requêtes rapides, compression efficace |
| **Avro**    | Ligne       | Streaming, transactions   | Sérialisation rapide, intégration avec Kafka |

---

### **🎯 Quand choisir Parquet ou Avro ?**
🔹 **Utilise Parquet** pour les **analyses de grandes bases** de données.  
🔹 **Utilise Avro** pour les **transactions et le streaming**.  

Ces formats sont essentiels pour **optimiser le stockage et les performances des données** .

