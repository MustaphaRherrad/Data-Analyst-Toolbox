# Graphiques_interactifs_Plotly.md

## Introduction

Plotly est une bibliothèque Python puissante qui permet de créer des **graphiques interactifs** facilement.

### 1. **Installation**
Si ce n'est pas encore fait, installe Plotly avec :
```python
pip install plotly
```

### 2. **Importer la bibliothèque**
```python
import plotly.express as px
import plotly.graph_objects as go
```

### 3. **Créer un graphique interactif simple**
```python
df = px.data.gapminder()

fig = px.scatter(df, x="gdpPercap", y="lifeExp", color="continent",
                 size="pop", hover_name="country", animation_frame="year",
                 log_x=True, title="Évolution du PIB et de l'espérance de vie")
fig.show()
```
Ce graphique interactif permet de visualiser l'évolution du PIB et de l'espérance de vie par pays.

### 4. **Créer un graphique personnalisé avec `go.Figure`**
```python
fig = go.Figure()

fig.add_trace(go.Scatter(x=[1, 2, 3, 4], y=[10, 15, 7, 12],
                         mode='lines+markers', name='Courbe'))

fig.update_layout(title="Graphique interactif avec Plotly",
                  xaxis_title="X-axis", yaxis_title="Y-axis")
fig.show()
```

### 5. **Explorer davantage**
Tu peux consulter la documentation officielle de [Plotly](https://plotly.com/python/) pour découvrir plus de fonctionnalités et d'exemples.
