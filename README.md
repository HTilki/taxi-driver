# Taxi driver :taxi:

<img src="http://www.parisfaitsoncinema.com/cache/media/de-niro-590/cr%2C640%2C450-7f7085.jpg" width=40% height=40% align="right">

[![codecov](https://codecov.io/gh/Textualize/rich/branch/master/graph/badge.svg)](https://codecov.io/gh/Textualize/rich)

- Il s'agit d'un problème de graphe **non-orienté et pondéré** 
- Le graphe est non-orienté car pour chaque arrête $x - y$, il existe une arrête $y-x$ (on peut parcourir la route dans les deux sens)

## Présentation

La librairie `taxi-driver` permet de modéliser le problème suivant [(Lien vers le sujet)](https://github.com/CDucloux/Taxi-company/blob/main/Sujet.md) en termes de *graphe pondéré*.

Elle répondra aux exigeances suivantes :
- [x] Déterminer le chemin le plus court de la compagnie de taxi à l'aéroport
- [x] Déterminer les chemins les plus courts entre tous les points de la ville
- [x] Etudier l'impact d'un ralentissement ou d'une fluidification sur la route **9-13**
- [x] Les emplacements **(3,5,7,9,11)** sont en travaux $\Rightarrow$ Tout passage par un de ces lieux ajoute +1 minute au trajet

## Résolution



### Utilisation de la **Command Line Interface**

```python
py -m app emplacements
```

- Affiche la liste des emplacements disponibles de la ville.

```python
py -m app routes
```

- Affiche la liste des routes reliant des emplacements de la ville ainsi que leur durée de parcours, sous forme de tableau.

```python
py -m app routes --graphe
```
- Affiche la liste des routes reliant des emplacements de la ville ainsi que leur durée de parcours, sous forme de graphe.

```python
py -m app trajet départ arrivée
```

- Calcule l'itinéraire et le temps de trajet optimal entre les points de départ et d'arrivée spécifiés.

```python
py -m app bouchons départ arrivee durée
```

- Ajoute une durée de bouchon spécifiée par l'utilisateur sur une route. L'utilisateur peut ensuite recalculer un trajet 
- Il existe une option `--fluidification` pour fluidifier la route plutôt que de faire des bouchons.

```python
py -m app emplacement_1 emplacement_2 emplacement_n durée
```

- Ajoute dees travaux à un ou plusieurs emplacements avec une durée spécifiée par l'utilisateur. Il peut ensuite recalculer un trajet 

## Caractéristiques

- Module entièrement documenté sur l'interface publique et privée
- Formatage du code par `black` pour correspondre à la norme **PEP 8**
- Gestion des *dependencies* avec `poetry`
- Type checking avec `mypy`
- Création d'une `cli` avec `typer`
- Tests unitaires et tests d'intégrations avec `pytest` et couverture des tests avec `pytest-cov`

