# Cassandra.md

Cassandra est une **base de données NoSQL distribuée** conçue pour gérer de **grands volumes de données** avec une **haute disponibilité** et une **scalabilité horizontale**. Elle est particulièrement utilisée dans les systèmes nécessitant une **tolérance aux pannes** et une **performance élevée**.

### 1. **Caractéristiques principales**
- **Modèle clé-valeur et colonne** : permet un stockage efficace des données.
- **Architecture distribuée** : chaque nœud du cluster est indépendant, évitant les points de défaillance uniques.
- **Scalabilité horizontale** : possibilité d'ajouter des serveurs sans affecter les performances.
- **Tolérance aux pannes** : les données sont répliquées sur plusieurs nœuds pour assurer la disponibilité.
- **Langage CQL (Cassandra Query Language)** : similaire à SQL mais adapté aux bases NoSQL.

### 2. **Cas d'utilisation**
- **Big Data** : gestion de grandes quantités de données en temps réel.
- **Applications web et mobiles** : stockage rapide et flexible.
- **IoT (Internet des objets)** : collecte et traitement de données distribuées.
- **Analytique et recommandations** : utilisé par des entreprises comme Netflix et Facebook.

### 3. **Exemple de requêtes en CQL**
#### **Créer une table**
```sql
CREATE TABLE utilisateurs (
    id UUID PRIMARY KEY,
    nom TEXT,
    age INT
);
```

#### **Insérer des données**
```sql
INSERT INTO utilisateurs (id, nom, age) VALUES (uuid(), 'Alice', 30);
```

#### **Requêter des données**
```sql
SELECT * FROM utilisateurs WHERE age > 25;
```

### 4. **Ressources pour approfondir**
Tu peux explorer ces guides :
- [Documentation officielle de Cassandra](https://cassandra.apache.org/doc/latest/)
- [Tutoriel détaillé sur Cassandra](https://datascientest.com/apache-cassandra-tout-savoir)
- [Guide IBM sur les bases NoSQL](https://www.ibm.com/fr-fr/topics/nosql)
