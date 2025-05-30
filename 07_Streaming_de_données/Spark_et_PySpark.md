# Spark_et_PySpark.md

Apache Spark et PySpark sont des outils puissants pour le **traitement distribué des données**. Voici un aperçu de leurs fonctionnalités et de leur utilisation.

### 1. **Qu'est-ce qu'Apache Spark ?**
Apache Spark est un **framework open-source** conçu pour le **Big Data** et le **calcul distribué**. Il permet de traiter de **grandes quantités de données** rapidement grâce à son exécution en mémoire.

### 2. **Qu'est-ce que PySpark ?**
PySpark est l'API Python de Spark, qui permet aux **data analysts** et **data scientists** d'utiliser Spark avec Python. Il offre des fonctionnalités avancées comme :
- **Spark SQL** : manipulation de données avec SQL.
- **DataFrames** : gestion efficace des données tabulaires.
- **MLlib** : bibliothèque de Machine Learning.
- **Streaming** : traitement des flux de données en temps réel.

### 3. **Installation de PySpark**
```bash
pip install pyspark
```
Puis, pour démarrer PySpark :
```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("MonProjet").getOrCreate()
```

### 4. **Exemple de manipulation de données**
```python
from pyspark.sql import SparkSession
from pyspark.sql.functions import col

# Création d'une session Spark
spark = SparkSession.builder.appName("Exemple").getOrCreate()

# Chargement d'un DataFrame
df = spark.read.csv("data.csv", header=True, inferSchema=True)

# Filtrer les données
df_filtre = df.filter(col("age") > 30)

# Afficher les résultats
df_filtre.show()
```

### 5. **Ressources pour approfondir**
- [Tutoriel PySpark pour débutants](https://www.guru99.com/fr/pyspark-tutorial.html)
- [Guide complet sur PySpark](https://datascientest.com/pyspark)
- [Documentation officielle Apache Spark](https://spark.apache.org/docs/latest/api/python/index.html)
