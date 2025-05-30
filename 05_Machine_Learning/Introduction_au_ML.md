# Introduction_au_ML.md

Le **Machine Learning (ML)** est une branche de l'intelligence artificielle qui permet aux ordinateurs d'apprendre à partir de données et d'améliorer leurs performances sans être explicitement programmés.

### 1. **Définition et fonctionnement**
Le ML repose sur des algorithmes qui détectent des **patterns** dans les données et font des prédictions ou des décisions basées sur ces modèles. Il existe trois types principaux :
- **Apprentissage supervisé** : l'algorithme apprend à partir de données étiquetées.
- **Apprentissage non supervisé** : il découvre des structures cachées dans des données non étiquetées.
- **Apprentissage par renforcement** : il apprend par essais et erreurs pour maximiser une récompense.

### 2. **Principaux algorithmes**
- **Régression linéaire** : pour prédire une valeur continue.
- **Arbres de décision** : pour classer des données.
- **K-means** : pour regrouper des données similaires.
- **Réseaux de neurones** : pour des tâches complexes comme la reconnaissance d'images.

### 3. **Exemple en Python**
```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
import numpy as np

# Données fictives
X = np.array([1, 2, 3, 4, 5]).reshape(-1, 1)
y = np.array([2, 4, 6, 8, 10])

# Séparation des données
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Modèle de régression linéaire
model = LinearRegression()
model.fit(X_train, y_train)

# Prédiction
y_pred = model.predict(X_test)
print(y_pred)
```

### 4. **Ressources pour approfondir**
Tu peux explorer ces guides :
- [Introduction détaillée au Machine Learning](http://cazencott.info/dotclear/public/lectures/IntroML_Azencott.pdf)
- [Définition et fonctionnement du ML](https://datascientest.com/machine-learning-tout-savoir)
- [Cours interactif sur OpenClassrooms](https://openclassrooms.com/fr/courses/8063076-initiez-vous-au-machine-learning)
