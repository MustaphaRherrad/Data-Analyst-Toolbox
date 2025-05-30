# Régression.md

La **régression supervisée** est une technique de Machine Learning utilisée pour prédire une valeur continue à partir de données d'entraînement. Voici les concepts clés :

### 1. **Définition**
Contrairement à la classification qui attribue des catégories, la régression permet de prédire une **valeur numérique**. Exemples :
- Prédire le **prix d'une maison** en fonction de ses caractéristiques.
- Estimer la **température** en fonction des conditions météorologiques.

### 2. **Principaux algorithmes**
- **Régression linéaire** : modèle simple qui ajuste une droite aux données.
- **Régression polynomiale** : extension de la régression linéaire pour des relations non linéaires.
- **Régression Ridge et Lasso** : ajoutent une pénalité pour éviter le sur-apprentissage.
- **Régression SVR (Support Vector Regression)** : basée sur les SVM pour prédire des valeurs continues.
- **Réseaux de neurones** : adaptés aux relations complexes.

### 3. **Évaluation des modèles**
- **Erreur quadratique moyenne (MSE)** : mesure l'écart entre les prédictions et les valeurs réelles.
- **Erreur absolue moyenne (MAE)** : moyenne des écarts absolus.
- **R² (coefficient de détermination)** : indique la proportion de variance expliquée par le modèle.

### 4. **Exemple en Python**
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

### 5. **Ressources pour approfondir**
Tu peux explorer ces guides :
- [Les principaux algorithmes de régression](https://fr.linedata.com/les-principaux-algorithmes-de-regression-pour-lapprentissage-supervise)
- [Cours interactif sur la régression supervisée](https://labex.io/fr/courses/supervised-learning-regression)
- [Explication des modèles de Machine Learning](https://moncoachdata.com/blog/modeles-de-machine-learning-expliques/)
