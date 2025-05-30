# MongoDB.md

MongoDB est une **base de données NoSQL orientée documents**, conçue pour gérer de **grands volumes de données** avec une **flexibilité et une scalabilité élevées**.

### 1. **Caractéristiques principales**
- **Stockage sous forme de documents JSON/BSON** : permet une structure flexible sans schéma prédéfini.
- **Scalabilité horizontale** : les données peuvent être réparties sur plusieurs serveurs.
- **Indexation avancée** : améliore la rapidité des requêtes.
- **Tolérance aux pannes** : grâce à la réplication des données.
- **Langage de requête puissant** : basé sur JSON, avec des fonctionnalités avancées comme l'agrégation.

### 2. **Cas d'utilisation**
- **Big Data** : gestion de grandes quantités de données en temps réel.
- **Applications web et mobiles** : stockage rapide et flexible.
- **IoT (Internet des objets)** : collecte et traitement de données distribuées.
- **Analytique et recommandations** : utilisé par des entreprises comme Netflix et eBay.

### 3. **Exemple de requêtes en MongoDB**
#### **Connexion et insertion de données**
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

### 4. **Ressources pour approfondir**
Tu peux explorer ces guides :
- [Site officiel de MongoDB](https://www.mongodb.com/)
- [Explication détaillée sur Wikipédia](https://fr.wikipedia.org/wiki/MongoDB)
- [Guide complet sur MongoDB](https://datascientest.com/mongodb)
