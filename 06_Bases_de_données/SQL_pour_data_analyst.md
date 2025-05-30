# SQL_pour_data_analyst.md

SQL est un langage essentiel pour les **data analysts**, permettant de manipuler et d'extraire des données efficacement. Voici un aperçu des **concepts de base** et quelques **cas pratiques**.

### 1. **Concepts fondamentaux**
- **Bases de données relationnelles** : stockent les données sous forme de tables.
- **Tables** : composées de colonnes (attributs) et de lignes (enregistrements).
- **Requêtes SQL** : permettent d'interroger et de modifier les données.

### 2. **Requêtes de base**
#### **Sélectionner des données**
```sql
SELECT * FROM clients; -- Sélectionne toutes les colonnes
SELECT nom, age FROM clients WHERE age > 30; -- Filtre les clients de plus de 30 ans
```

#### **Filtrer et trier**
```sql
SELECT * FROM ventes WHERE montant > 1000 ORDER BY date DESC; -- Trie par date décroissante
```

#### **Agrégation et groupement**
```sql
SELECT categorie, COUNT(*) AS nombre_produits
FROM produits
GROUP BY categorie;
```

### 3. **Jointures entre tables**
#### **INNER JOIN (jointure interne)**
```sql
SELECT clients.nom, commandes.id_commande
FROM clients
INNER JOIN commandes ON clients.id_client = commandes.id_client;
```

#### **LEFT JOIN (jointure externe gauche)**
```sql
SELECT clients.nom, commandes.id_commande
FROM clients
LEFT JOIN commandes ON clients.id_client = commandes.id_client;
```

### 4. **Sous-requêtes et fonctions avancées**
#### **Sous-requête**
```sql
SELECT nom FROM clients WHERE id_client IN 
(SELECT id_client FROM commandes WHERE montant > 500);
```

#### **Fonctions de fenêtre**
```sql
SELECT nom, age, RANK() OVER (ORDER BY age DESC) AS classement
FROM clients;
```

### 5. **Ressources pour approfondir**
Tu peux explorer ces guides :
- [Tutoriel SQL pour Data Analysts](https://fr.tuto.com/sql/apprendre-sql-de-a-a-z-analyse-de-data-cas-pratiques-data-science-inclus,112181.html)
- [Requêtes SQL avancées](https://moncoachdata.com/blog/sql-pour-lanalyse-de-donnees/)
- [Concepts essentiels en SQL](https://learnsql.fr/blog/sql-pour-l-analyse-de-donnees-que-dois-je-apprendre/)
