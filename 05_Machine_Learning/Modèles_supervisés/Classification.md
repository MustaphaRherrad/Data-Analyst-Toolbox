# Classification.md

La **classification supervisée** est une technique de Machine Learning où un modèle apprend à partir de données étiquetées pour prédire une catégorie. Voici les principaux concepts :

### 1. **Définition**
La classification consiste à attribuer une **étiquette** à une donnée en fonction de ses caractéristiques. Exemples :
- Déterminer si un email est **spam** ou **non-spam**.
- Prédire si un client va **acheter** ou **ne pas acheter** un produit.

### 2. **Principaux algorithmes**
- **Régression logistique** : utilisée pour des classifications binaires.
- **Arbres de décision** : modèle basé sur des règles de décision.
- **Random Forest** : ensemble d’arbres de décision pour améliorer la précision.
- **Support Vector Machine (SVM)** : trouve une frontière optimale entre classes.
- **Naive Bayes** : basé sur la probabilité conditionnelle.
- **Réseaux de neurones** : adaptés aux classifications complexes.

### 3. **Évaluation des modèles**
- **Précision** : proportion de prédictions correctes.
- **Rappel** : capacité à identifier les cas positifs.
- **F1-score** : équilibre entre précision et rappel.
- **Matrice de confusion** : tableau des erreurs de classification.

### 4. **Exemple en Python**
```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score
import numpy as np

# Données fictives
X = np.random.rand(100, 3)
y = np.random.randint(0, 2, 100)

# Séparation des données
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Modèle de classification
model = RandomForestClassifier()
model.fit(X_train, y_train)

# Prédiction et évaluation
y_pred = model.predict(X_test)
print("Précision :", accuracy_score(y_test, y_pred))
```

### 5. **Ressources pour approfondir**
Tu peux explorer ces guides :
- [Explication des modèles supervisés](https://moncoachdata.com/blog/modeles-de-machine-learning-expliques/)
- [Principaux algorithmes de classification](https://datascientest.com/algorithme-de-classification-definition-et-principaux-modeles)
- [Évaluation avancée des modèles](https://openclassrooms.com/fr/courses/8431846-maitrisez-lapprentissage-supervise/8501411-evaluez-de-maniere-plus-poussee-vos-modeles-de-classification)
