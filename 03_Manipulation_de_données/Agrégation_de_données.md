L’**agrégation de données** est une technique essentielle pour **résumer, regrouper et analyser** des informations dans un dataset. Elle est souvent utilisée en **statistiques, Data Science et Business Intelligence** pour extraire des tendances.  

---

## 📊 **1. Pourquoi utiliser l’agrégation de données ?**  
L’agrégation permet de :  
✅ **Synthétiser l’information** → Résumer de grandes quantités de données.  
✅ **Comparer des groupes** → Par exemple, analyser les ventes par région.  
✅ **Faciliter l’analyse statistique** → Calculer des moyennes, des médianes, des écarts-types.  

---

## 📌 **2. Agrégation avec Pandas en Python**  

### **🔹 GroupBy : Regrouper et calculer des statistiques**  
La méthode `groupby()` permet de **regrouper les données** selon une colonne, puis d’appliquer **une fonction statistique** :  

```python
import pandas as pd

# Exemple de dataset
data = {"Ville": ["Paris", "Lyon", "Paris", "Marseille", "Lyon"],
        "Ventes": [1000, 1500, 2000, 1800, 1700]}

df = pd.DataFrame(data)

# Regrouper par Ville et calculer la somme des ventes
df_grouped = df.groupby("Ville")["Ventes"].sum()

print(df_grouped)
```
✅ **Résultat** : Total des ventes par ville.  

---

### **🔹 Agrégation avec plusieurs fonctions**  
Tu peux appliquer **plusieurs statistiques** en une seule commande :  

```python
df_grouped = df.groupby("Ville")["Ventes"].agg(["mean", "sum", "count"])
print(df_grouped)
```
✅ Cela donne **la moyenne, le total et le nombre d’occurrences** par ville.  

---

### **🔹 Pivot Table : Agrégation avancée**  
Les **tables pivot** permettent de **résumer les données** efficacement :  

```python
df_pivot = df.pivot_table(values="Ventes", index="Ville", aggfunc=["sum", "mean"])
print(df_pivot)
```
✅ **Alternative** à `groupby()`, surtout utilisée en **Business Intelligence**.  

---

## 🔄 **3. Filtrer et appliquer des conditions sur l’agrégation**  

Tu peux filtrer les groupes avant d’agréger les données :  

```python
df_filtre = df[df["Ventes"] > 1500]
df_grouped = df_filtre.groupby("Ville")["Ventes"].sum()

print(df_grouped)
```
✅ Ici, seules les **villes avec des ventes > 1500** sont analysées.  

---

## 📈 **4. Visualiser les données agrégées**  

### **🔹 Diagramme en barres des ventes par ville**
```python
import matplotlib.pyplot as plt

df_grouped.plot(kind="bar", title="Total des ventes par ville")
plt.show()
```
✅ **Représentation graphique** pour mieux analyser les résultats.  

---

## 🔥 **Résumé**
| **Méthode** | **Usage** | **Exemple Python** |
|------------|---------|----------------|
| `groupby()` | Regrouper et agréger | `df.groupby("Ville")["Ventes"].sum()` |
| `agg()` | Appliquer plusieurs statistiques | `df.groupby("Ville")["Ventes"].agg(["mean", "sum"])` |
| `pivot_table()` | Agrégation avancée | `df.pivot_table(values="Ventes", index="Ville", aggfunc="sum")` |
| `plot()` | Visualisation | `df_grouped.plot(kind="bar")` |

---

Avec ces techniques, tu peux **gagner en efficacité** et **extraire des insights précieux** de tes données !
