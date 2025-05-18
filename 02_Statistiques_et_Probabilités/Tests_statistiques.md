# Tests_statistiques.md

Les **tests statistiques** sont indispensables pour **valider des hypothèses et comparer des données** en Data Science et analyse de données. 🚀  

---

## 📊 **1. Introduction aux tests statistiques**  
Les **tests statistiques** permettent de vérifier **si une hypothèse sur un ensemble de données est valide**.  
Ils servent à comparer **des moyennes, des proportions, des distributions** et à déterminer **si une différence observée est significative ou due au hasard**.  

### **🔹 Concepts essentiels**
- **Hypothèse nulle (`H₀`)** → Il n’y a **pas de différence significative** entre les groupes.  
- **Hypothèse alternative (`H₁`)** → Il y a une **différence significative**.  
- **p-value** → Probabilité d’obtenir le résultat observé **si `H₀` est vraie**.  
  - **Si `p < 0.05` → Rejet de `H₀`** (différence significative).  
  - **Si `p > 0.05` → On ne rejette pas `H₀`** (pas de différence évidente).  

---

## 📌 **2. Principaux tests statistiques**  
### **🔹 Test de Student (t-test)**
✅ **Objectif** : Comparer **les moyennes** de deux groupes.  
✅ **Exemple** : Comparer les notes moyennes de **deux classes** après un examen.  

Exemple en Python :  
```python
import scipy.stats as stats

group1 = [12, 15, 14, 17, 13, 16, 14]
group2 = [10, 12, 11, 14, 10, 12, 13]

# Test de Student
t_stat, p_value = stats.ttest_ind(group1, group2)

print(f"T-statistic : {t_stat}, p-value : {p_value}")
```

---

### **🔹 Test du khi-deux (Chi-square)**
✅ **Objectif** : Vérifier **la relation entre deux variables catégorielles**.  
✅ **Exemple** : Est-ce que le choix d’un produit dépend du genre du client ?  

Exemple en Python :  
```python
import numpy as np
from scipy.stats import chi2_contingency

# Tableau de contingence (Fréquences observées)
table = np.array([[50, 30], [20, 40]])  # Ex. : (Hommes/Femmes achetant un produit)

# Test du Khi-deux
chi2_stat, p_value, dof, expected = chi2_contingency(table)

print(f"Chi-square statistic : {chi2_stat}, p-value : {p_value}")
```

---

### **🔹 ANOVA (Analyse de Variance)**
✅ **Objectif** : Comparer **plus de deux groupes** (extension du t-test).  
✅ **Exemple** : Comparer les performances de **trois formations différentes**.  

Exemple en Python :  
```python
group1 = [12, 15, 14, 17, 13]
group2 = [10, 12, 11, 14, 10]
group3 = [14, 18, 15, 19, 16]

# Test ANOVA
anova_stat, p_value = stats.f_oneway(group1, group2, group3)

print(f"ANOVA statistic : {anova_stat}, p-value : {p_value}")
```

---

### **🔹 Test de corrélation (Pearson)**
✅ **Objectif** : Mesurer **la relation entre deux variables numériques**.  
✅ **Exemple** : Y a-t-il un lien entre **le revenu et les dépenses** d’un client ?  

Exemple en Python :  
```python
revenu = [2000, 2500, 2800, 3000, 3200]
depenses = [1500, 1600, 1800, 2000, 2200]

# Test de corrélation de Pearson
corr, p_value = stats.pearsonr(revenu, depenses)

print(f"Coefficient de corrélation : {corr}, p-value : {p_value}")
```

---

## **🚀 Interprétation des résultats**
🔹 **Si `p-value < 0.05` → Rejet de `H₀`** → **Les groupes sont différents** ou **il y a une relation significative**.  
🔹 **Si `p-value > 0.05` → On ne rejette pas `H₀`** → **Aucune différence significative** ou **pas de relation évidente**.  

---

## 🔥 **Résumé**
| **Test** | **Objectif** | **Exemple** | **Python** |
|----------|-------------|-------------|------------|
| **t-test** | Comparer 2 moyennes | Notes moyennes de 2 classes | `stats.ttest_ind()` |
| **Chi²** | Relation entre 2 variables catégorielles | Sexe et choix de produit | `stats.chi2_contingency()` |
| **ANOVA** | Comparer 3 groupes ou plus | Performances de 3 formations | `stats.f_oneway()` |
| **Corrélation** | Relation entre 2 variables numériques | Revenu et dépenses | `stats.pearsonr()` |

---

Avec ces tests statistiques, tu peux **valider des hypothèses**, **comparer des populations** et **analyser des tendances** dans tes données ! 
