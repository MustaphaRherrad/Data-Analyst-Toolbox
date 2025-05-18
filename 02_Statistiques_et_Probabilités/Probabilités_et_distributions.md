# Probabilités_et_distributions.md

Je vous présente un petit **tutoriel clair et structuré** sur les **probabilités et distributions**, des concepts fondamentaux en **statistiques et Data Science**. 

---

## 📊 **1. Notions de base en probabilités**  
Les probabilités permettent de **quantifier l’incertitude** et d’évaluer la **chance** qu’un événement se produise.

### **🔹 Expériences aléatoires**  
Une **expérience aléatoire** est une expérience dont le résultat **n’est pas prévisible avec certitude**. 
Exemple :  
- **Lancer un dé** → On ne sait pas quel chiffre va sortir de 1 à 6.  
- **Tirer une carte dans un jeu** → Chaque carte a une certaine probabilité d’être tirée.  

### **🔹 Notions fondamentales**  
- **Événement** : Résultat possible d’une expérience (ex. : obtenir un "6" sur un dé).  
- **Espace des événements** (`Ω`) : Ensemble de **tous les résultats possibles** (ex. : {1,2,3,4,5,6} pour un dé).  
- **Probabilité d’un événement** (`P(E)`) : Nombre entre **0** et **1** indiquant la chance qu’un événement se réalise.  
  - **0** → Impossible  
  - **1** → Certain  
  - **Entre 0 et 1** → Possible avec une probabilité donnée  

💡 **Formule de base** :  
Si tous les événements sont **équiprobables** c'est-à-dire qu'ils tous la même chance de soritr, alors la probabilité d’un événement `E` est :  
\[
P(E) = \frac{\text{Nombre de cas favorables}}{\text{Nombre de cas possibles}}
\]

---

## 📉 **2. Distributions de probabilité**  
Les **distributions de probabilité** décrivent **comment** les valeurs d’une variable aléatoire sont réparties.

### **🔹 Types de variables aléatoires**  
- **Variable aléatoire discrète** → Prend un **nombre limité** de valeurs (ex. : lancer de dé).  
- **Variable aléatoire continue** → Prend une **infinité** de valeurs (ex. : la température).  

---

### **📌 3. Principales distributions de probabilité**  

#### **🔹 Loi Uniforme**  
Chaque valeur a la **même probabilité** d’être choisie.  
Exemple : Un **dé équilibré** → Chaque face a `1/6` de chances d’apparaître.  

#### **🔹 Loi de Bernoulli**  
Modélise un événement avec **deux résultats possibles** (`succès` ou `échec`).  
Exemple : **Pile ou face** → `P(Pile) = 0.5`, `P(Face) = 0.5`.

#### **🔹 Loi Binomiale**  
Modélise le nombre de **succès** dans une série d’expériences indépendantes.  
Exemple : **Nombre de "6" obtenus en lançant 10 dés**.

\[
P(k) = C(n, k) p^k (1 - p)^{n - k}
\]
où :
- `C(n, k)` → Nombre de façons de choisir `k` succès parmi `n` essais.  
- `p` → Probabilité de succès.  
- `k` → Nombre de succès recherchés.  

#### **🔹 Loi Normale (Gaussienne)**  
La plus importante ! Modélise les phénomènes **naturels** et **sociaux**. Elle suit une **courbe en cloche** définie par :  

\[
f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{(x - \mu)^2}{2\sigma^2}}
\]

où :
- `μ` → Moyenne  
- `σ` → Écart-type  

Elle est omniprésente en **science des données** et en **modélisation statistique**.

---

### **📌 4. Illustration en Python**  
On peux **visualiser ces distributions** avec **Pandas & Matplotlib** !  

```python
import numpy as np
import matplotlib.pyplot as plt
import scipy.stats as stats

# Génération de données normales
data = np.random.normal(loc=0, scale=1, size=1000)

# Tracer l’histogramme
plt.hist(data, bins=30, density=True, alpha=0.6, color='b')

# Tracer la fonction de densité normale
xmin, xmax = plt.xlim()
x = np.linspace(xmin, xmax, 100)
p = stats.norm.pdf(x, 0, 1)
plt.plot(x, p, 'k', linewidth=2)

plt.title("Distribution Normale")
plt.show()
```

---

## **🎯 Conclusion**
Les **probabilités et distributions** sont **essentielles** en Data Science et en analyse statistique !  

✔️ **Probabilités** → Quantifient l’incertitude.  
✔️ **Distributions** → Modélisent la répartition des valeurs.  
✔️ **Loi Normale** → Pilier des statistiques.  


