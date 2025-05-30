# Requêtes_avancées.md

Les **requêtes SQL avancées** permettent d'exploiter pleinement les bases de données relationnelles en optimisant la récupération et la manipulation des données. Voici quelques concepts et exemples pratiques :

### 1. **Sous-requêtes et requêtes imbriquées**
Les sous-requêtes permettent d'exécuter une requête à l'intérieur d'une autre.
```sql
SELECT nom, salaire FROM employes
WHERE salaire > (SELECT AVG(salaire) FROM employes);
```
Cette requête sélectionne les employés dont le salaire est supérieur à la moyenne.

### 2. **Jointures complexes**
Les jointures permettent de combiner des données provenant de plusieurs tables.
```sql
SELECT clients.nom, commandes.id_commande, commandes.montant
FROM clients
JOIN commandes ON clients.id_client = commandes.id_client
WHERE commandes.montant > 1000;
```
Ici, on récupère les commandes de plus de 1000€ avec les noms des clients.

### 3. **Fonctions de fenêtre**
Les fonctions de fenêtre permettent d'effectuer des calculs sur un ensemble de lignes sans les regrouper.
```sql
SELECT nom, salaire, RANK() OVER (ORDER BY salaire DESC) AS classement
FROM employes;
```
Cette requête classe les employés selon leur salaire.

### 4. **Requêtes récursives (CTE)**
Les **Common Table Expressions (CTE)** permettent de gérer des relations hiérarchiques.
```sql
WITH Hierarchie AS (
    SELECT id, nom, manager_id FROM employes WHERE manager_id IS NULL
    UNION ALL
    SELECT e.id, e.nom, e.manager_id FROM employes e
    JOIN Hierarchie h ON e.manager_id = h.id
)
SELECT * FROM Hierarchie;
```
Cette requête récupère la hiérarchie des employés.

### 5. **Manipulation de données JSON**
Certaines bases SQL modernes permettent de manipuler des données JSON.
```sql
SELECT json_extract(data, '$.nom') AS nom_client
FROM commandes;
```
Cette requête extrait le nom du client depuis une colonne contenant des données JSON.

### 6. **Optimisation des requêtes**
- **Indexation** : améliore la rapidité des recherches.
- **Partitionnement** : divise les données pour optimiser les performances.
- **Analyse des plans d'exécution** : permet d'identifier les goulots d'étranglement.

Tu peux approfondir ces concepts avec [cet article](https://learnsql.fr/blog/25-exemples-de-requetes-sql-avancees/) et [ce guide détaillé](https://moncoachdata.com/blog/top-10-des-requetes-sql-avancees/). 