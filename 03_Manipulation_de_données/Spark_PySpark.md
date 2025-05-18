**Apache Spark** est un framework open-source pour le **traitement de données massives**. **PySpark** est son interface Python, permettant d’utiliser Spark avec des **DataFrames, SQL et Machine Learning**.

---

## ✅ **1. Installation de PySpark**  

### **🔹 Installer PySpark avec pip**
Si PySpark n’est pas installé, ajoute-le via **pip** :  
```bash
pip install pyspark
```

### **🔹 Vérifier l’installation**  
Dans Python, vérifie que PySpark fonctionne :  
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("TestSpark").getOrCreate()
print(spark.version)  # Affiche la version installée
```

---

## 📦 **2. Création d’une session Spark**  

### **🔹 Démarrer Spark**
```python
spark = SparkSession.builder.appName("MonAnalyse").getOrCreate()
```

---

## 📊 **3. Manipulation des DataFrames avec PySpark**  

### **🔹 Charger un fichier CSV**
```python
df = spark.read.csv("data.csv", header=True, inferSchema=True)
df.show()
```

### **🔹 Afficher la structure des données**
```python
df.printSchema()
df.describe().show()
```

### **🔹 Sélectionner des colonnes**
```python
df.select("Nom", "Âge").show()
```

### **🔹 Filtrer les données**
```python
df_filtre = df.filter(df["Âge"] > 30)
df_filtre.show()
```

---

## 🔄 **4. Groupement et agrégation**  

### **🔹 Calculer la moyenne par groupe**
```python
df_grouped = df.groupBy("Ville").agg({"Salaire": "mean"})
df_grouped.show()
```

### **🔹 Trier les résultats**
```python
df.orderBy(df["Salaire"].desc()).show()
```

---

## 🚀 **5. Exécution de requêtes SQL**  

### **🔹 Créer une table temporaire**
```python
df.createOrReplaceTempView("employes")
```

### **🔹 Exécuter une requête SQL**
```python
df_sql = spark.sql("SELECT Nom, Age FROM employes WHERE Age > 30")
df_sql.show()
```

---

## 📈 **6. Manipulation avancée avec Spark MLlib**  

### **🔹 Appliquer une transformation avec VectorAssembler**
```python
from pyspark.ml.feature import VectorAssembler

assembler = VectorAssembler(inputCols=["Age", "Salaire"], outputCol="features")
df_vect = assembler.transform(df)
df_vect.show()
```

### **🔹 Appliquer un modèle de régression**
```python
from pyspark.ml.regression import LinearRegression

lr = LinearRegression(featuresCol="features", labelCol="Salaire")
model = lr.fit(df_vect)
predictions = model.transform(df_vect)
predictions.show()
```

---

## 🔥 **Résumé**
| **Fonctionnalité** | **Commande** |
|----------------|------------|
| **Installation** | `pip install pyspark` |
| **Créer une session** | `SparkSession.builder.appName("Nom").getOrCreate()` |
| **Charger CSV** | `spark.read.csv("data.csv", header=True)` |
| **Filtrer les données** | `df.filter(df["Âge"] > 30)` |
| **Requêtes SQL** | `spark.sql("SELECT * FROM table")` |
| **Machine Learning** | `from pyspark.ml.regression import LinearRegression` |

---

Avec **PySpark**, tu peux manipuler **d’énormes volumes de données** et faire du **Big Data Analytics** ! 
