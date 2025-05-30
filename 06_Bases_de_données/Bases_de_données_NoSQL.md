# Bases_de_données_NoSQL.md

Les **bases de données NoSQL** sont des systèmes de gestion de bases de données qui ne suivent pas le modèle relationnel classique. Elles sont conçues pour gérer de **grands volumes de données**, souvent non structurées, et offrent une **grande flexibilité** et **scalabilité**.

### 1. **Caractéristiques principales**
- **Absence de schéma fixe** : les données peuvent être stockées sous différentes formes (documents, colonnes, graphes, clés-valeurs).
- **Scalabilité horizontale** : possibilité d'ajouter des serveurs pour gérer plus de données.
- **Performance optimisée** : adaptées aux applications nécessitant des accès rapides et massifs.
- **Tolérance aux pannes** : les données sont souvent distribuées sur plusieurs serveurs.

### 2. **Types de bases NoSQL**
- **Bases orientées documents** : stockent des données sous forme de documents JSON ou BSON (ex. : MongoDB).
- **Bases orientées colonnes** : optimisées pour les requêtes massives sur des colonnes (ex. : Apache Cassandra).
- **Bases orientées graphes** : adaptées aux relations complexes entre données (ex. : Neo4j).
- **Bases clé-valeur** : stockent des paires clé-valeur pour des accès rapides (ex. : Redis).

### 3. **Cas d'utilisation**
- **Big Data** : gestion de grandes quantités de données en temps réel.
- **Applications web et mobiles** : stockage flexible et rapide.
- **Analyse de réseaux sociaux** : gestion des relations entre utilisateurs.
- **IoT (Internet des objets)** : collecte et traitement de données en continu.

### 4. **Exemple avec MongoDB**
```python
from pymongo import MongoClient

# Connexion à la base de données
client = MongoClient("mongodb://localhost:27017/")
db = client["ma_base"]
collection = db["utilisateurs"]

# Insertion d'un document
utilisateur = {"nom": "Alice", "age": 30, "ville": "Paris"}
collection.insert_one(utilisateur)

# Requête
resultat = collection.find_one({"nom": "Alice"})
print(resultat)
```

### 5. **Ressources pour approfondir**
Tu peux explorer ces guides :
- [Introduction aux bases NoSQL](https://datascientest.com/nosql-tout-savoir)
- [Explication détaillée sur Wikipédia](https://fr.wikipedia.org/wiki/NoSQL)
- [Guide IBM sur NoSQL](https://www.ibm.com/fr-fr/think/topics/nosql-databases)
