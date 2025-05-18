# Statistiques_descriptives.md

Les **statistiques descriptives** representent un outil essentiel pour **résumer, analyser et interpréter des données** en Data Science et en analyse de données.  

---

## 📊 **1. Définition des statistiques descriptives**  
Les statistiques descriptives permettent de **résumer et organiser** des ensembles de données sans faire de prédictions. Elles sont utilisées pour **comprendre la distribution** des valeurs et identifier les **tendances principales**.  

Elles incluent :  
✅ **Mesures de tendance centrale** (moyenne, médiane, mode).  
✅ **Mesures de dispersion** (variance, écart-type, étendue).  
✅ **Mesures de position** (quartiles, percentiles).  
✅ **Représentations graphiques** (histogrammes, boxplots).  

---

## 📌 **2. Mesures de tendance centrale**  
### **🔹 Moyenne**
\[
\mu = \frac{\sum{x_i}}{n}
\]
La moyenne est **la valeur centrale** d'un ensemble de données.  

Exemple en Python :  
```python
import numpy as np

data = [10, 12, 15, 14, 10, 8, 9, 13]
mean = np.mean(data)
print(f"Moyenne : {mean}")
```

---

### **🔹 Médiane**  
La médiane est **la valeur centrale** lorsque les données sont triées.  
- Si `n` est impair → C'est la valeur du milieu.  
- Si `n` est pair → C'est la **moyenne des deux valeurs centrales**.  

Exemple en Python :
```python
median = np.median(data)
print(f"Médiane : {median}")
```

---

### **🔹 Mode**  
Le mode est **la valeur la plus fréquente** dans un ensemble de données.  

Exemple en Python :
```python
from scipy import stats

mode = stats.mode(data)
print(f"Mode : {mode.mode[0]}")
```

---

## 📌 **3. Mesures de dispersion**  
### **🔹 Écart-type**
\[
\sigma = \sqrt{\frac{\sum (x_i - \mu)^2}{n}}
\]
L'écart-type mesure **la variation des valeurs** autour de la moyenne.  

Exemple en Python :
```python
std_dev = np.std(data)
print(f"Écart-type : {std_dev}")
```

---

### **🔹 Variance**
\[
\sigma^2 = \frac{\sum (x_i - \mu)^2}{n}
\]
La variance exprime **l'étendue de la dispersion** des données.  

Exemple en Python :
```python
variance = np.var(data)
print(f"Variance : {variance}")
```

---

### **🔹 Étendue (Range)**  
L’étendue correspond à **la différence entre la valeur max et min**.  

Exemple en Python :
```python
range_value = max(data) - min(data)
print(f"Étendue : {range_value}")
```

---

## 📌 **4. Quartiles et Boxplot**  
Les **quartiles** divisent les données en **quatre parties égales** :  
- **Q1 (25%)** → Premier quartile  
- **Q2 (50%)** → Médiane  
- **Q3 (75%)** → Troisième quartile  

Exemple en Python :
```python
q1 = np.percentile(data, 25)
q3 = np.percentile(data, 75)
print(f"Q1 : {q1}, Q3 : {q3}")
```

**Visualisation avec un boxplot** :
```python
import matplotlib.pyplot as plt

plt.boxplot(data)
plt.title("Boxplot des données")
plt.show()
```

---

## 🔥 **Résumé**
| **Concept** | **Définition** | **Formule** | **Python** |
|------------|--------------|------------|-----------|
| **Moyenne** | Valeur centrale | \(\mu = \frac{\sum{x_i}}{n}\) | `np.mean(data)` |
| **Médiane** | Milieu des données | - | `np.median(data)` |
| **Mode** | Valeur la plus fréquente | - | `stats.mode(data)` |
| **Variance** | Dispersion des valeurs | \(\sigma^2 = \frac{\sum (x_i - \mu)^2}{n}\) | `np.var(data)` |
| **Écart-type** | Variation autour de la moyenne | \(\sigma = \sqrt{\sigma^2}\) | `np.std(data)` |
| **Quartiles** | Division en 4 parties | - | `np.percentile(data, 25)` |

---

Ces concepts sont **essentiels** pour bien comprendre et interpréter des données avant d'appliquer des modèles statistiques ou d’apprentissage automatique !
