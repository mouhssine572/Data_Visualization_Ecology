# Data_Visualization_eco
Visualization for ecological data
https://disguisehub-1.my.canva.site/sae-groupe7
# Rapport Power BI et Script Python - Groupe 7

**Membres du Groupe :**
- Evan Lamour
- Maxime Planques
- Duc Hui
- Mouhssine Bairoune

## Introduction

Ce projet combine l'utilisation de Power BI et d'un script Python pour analyser les données relatives au réchauffement climatique. L'objectif est de fournir une analyse approfondie en visualisant des données complexes et en appliquant des transformations de données pour obtenir des informations significatives.

## Power BI

Power BI est une suite d'outils d'analyse de données développée par Microsoft. Il permet de créer des rapports interactifs et des tableaux de bord à partir de diverses sources de données. Pour ce projet, nous avons utilisé Power BI pour :

- **Créer des visualisations interactives** : Graphiques, cartes et indicateurs montrant l'évolution du rejet de CO2, des températures, des catastrophes naturelles, et d'autres aspects liés au changement climatique.
- **Analyser les tendances** : Examiner les données sur une période prolongée pour identifier les tendances et les anomalies.
- **Comparer les données** : Analyser les émissions de CO2 par pays et continent, et comparer les données démographiques avec les niveaux de pollution.

## Script Python

Le script Python fourni est utilisé pour préparer et transformer les données avant leur importation dans Power BI. Voici un aperçu des principales fonctionnalités du script :

- **Collecte des Données** : Le script récupère les données brutes à partir de diverses sources, telles que des fichiers CSV ou des API.
- **Préparation des Données** : Transformation des données en utilisant des bibliothèques comme `pandas` pour nettoyer et structurer les données. Cela inclut la gestion des types de données, le traitement des valeurs manquantes, et la normalisation des données.
- **Calcul des Métriques** : Le script calcule des métriques clés telles que les pourcentages de documents annulés, les moyennes de température, et d'autres indicateurs pertinents.
- **Exportation des Données** : Les données transformées sont exportées sous un format compatible avec Power BI, comme des fichiers CSV ou des bases de données.

### Exemple de Script Python

Voici un exemple simplifié de script Python utilisé pour transformer les données :

```python
import pandas as pd

# Chargement des données
data = pd.read_csv('data.csv')

# Nettoyage des données
data.dropna(inplace=True)
data['Date'] = pd.to_datetime(data['Date'])

# Calcul des pourcentages
data['Annulé_Pourcentage'] = (data['Documents_Annulés'] / data['Documents_Total']) * 100

# Exportation des données transformées
data.to_csv('data_transformed.csv', index=False)
