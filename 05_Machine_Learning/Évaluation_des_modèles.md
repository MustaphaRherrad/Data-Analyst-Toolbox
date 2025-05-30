# Évaluation_des_modèles.md

L'évaluation des modèles de **Machine Learning** est essentielle pour mesurer leur performance et leur capacité à généraliser sur de nouvelles données. Voici les principales méthodes et métriques utilisées :

### 1. **Validation croisée**
La **validation croisée** permet de tester un modèle sur plusieurs sous-ensembles de données pour éviter le sur-apprentissage. La méthode la plus courante est la **validation croisée en k-folds**, où les données sont divisées en k parties et le modèle est entraîné k fois avec des ensembles de test différents.

### 2. **Métriques de performance**
Les métriques varient selon le type de problème :
- **Régression** :
  - **Erreur quadratique moyenne (MSE)** : mesure l'écart entre les prédictions et les valeurs réelles.
  - **Erreur absolue moyenne (MAE)** : moyenne des écarts absolus entre les prédictions et les valeurs réelles.
  - **R² (coefficient de détermination)** : indique la proportion de variance expliquée par le modèle.

- **Classification** :
  - **Précision** : proportion de prédictions correctes.
  - **Rappel** : capacité du modèle à identifier les cas positifs.
  - **F1-score** : moyenne harmonique entre précision et rappel.
  - **Matrice de confusion** : tableau qui montre les erreurs de classification.

### 3. **Courbes et visualisations**
- **Courbe ROC & AUC** : utilisée pour évaluer les modèles de classification binaire.
- **Courbe de calibration** : montre la fiabilité des probabilités prédites.
- **Courbe d'apprentissage** : permet de détecter le sur-apprentissage ou le sous-apprentissage.

### 4. **Optimisation et ajustement**
- **Réglage des hyperparamètres** : utiliser des techniques comme la **recherche par grille** ou la **recherche bayésienne**.
- **Réduction du sur-apprentissage** : appliquer la **régularisation** ou collecter plus de données.

Tu peux approfondir ces concepts avec [cet article](https://www.saagie.com/fr/blog/machine-learning-comment-evaluer-vos-modeles-analyses-et-metriques/) et [ce guide détaillé](https://datascientest.com/metriques-en-machine-learning). 