# Matplotlib_et_Seaborn.md

## Introduction

**Matplotlib** et **Seaborn** sont deux bibliothèques Python puissantes pour la visualisation.

### 1. **Installation**
Si ce n'est pas encore fait, installe ces bibliothèques avec :
```python
pip install matplotlib seaborn
```

### 2. **Importer les bibliothèques**
```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
import pandas as pd
```

### 3. **Créer un graphique simple avec Matplotlib**
```python
x = np.linspace(0, 10, 100)
y = np.sin(x)

plt.plot(x, y, label="sin(x)", color="blue")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.title("Courbe Sinus")
plt.legend()
plt.show()
```

### 4. **Visualisation avancée avec Seaborn**
Seaborn facilite la création de graphiques esthétiques avec moins de code :
```python
# Charger un dataset exemple
df = sns.load_dataset("penguins")

# Diagramme de dispersion
sns.scatterplot(x="bill_length_mm", y="bill_depth_mm", hue="species", data=df)
plt.title("Relation entre la longueur et la profondeur du bec")
plt.show()
```

### 5. **Personnalisation des graphiques**
Seaborn permet de personnaliser facilement les graphiques :
```python
sns.set_style("whitegrid")
sns.histplot(df["bill_length_mm"], bins=20, kde=True)
plt.title("Distribution de la longueur du bec")
plt.show()
```
s
### 6. **Ressources supplémentaires**
Tu peux approfondir avec ces vidéos :
- [Visualisation de données avec Matplotlib et Seaborn](https://www.youtube.com/watch?v=J3cO3VyQXlc)
- [Tutoriel complet sur Matplotlib et Seaborn](https://www.youtube.com/watch?v=a9YzJL5p4ic)
- [Guide détaillé sur la visualisation en Python](https://www.datacamp.com/fr/tutorial/seaborn-python-tutorial)

