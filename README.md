# Analyse Statistique : MOOC Effectuation

Ce projet s'inscrit dans le cadre du cours d'introduction aux Statistiques de Cy Tech et Sciences-Po Saint-Germain-En-Laye. Il vise à reproduire les résultats de l'article *"A Tale of Two MOOCs"* (2015) à partir de données d’engagement d’apprenants.


## Objectifs

- Préparer et fusionner les jeux de données issus de différentes itérations du MOOC
- Construire une typologie d’apprenants (Completers, Disengaging, Auditing, Bystanders)
- Réaliser des analyses statistiques : Chi², ANOVA, régressions linéaire et logistique, loi de Poisson
- Diagnostiquer les modèles et interpréter les résultats

## Technologies utilisés
- **Langage** : R
- **Bibliothèques principales** : 
  - `dplyr`, `tidyr` : Manipulation de données
  - `ggplot2`, `patchwork` : Visualisation
  - `vcd`, `vcdExtra` : Analyses catégorielles et mosaic plots
  - `car`, `broom` : Diagnostics de modèles
  - `forestplot` : Représentation graphique des odds ratios

## Installation

### Cloner le repository

```bash
git clone https://github.com/naima-beck/analyse-statistique-engagement-mooc.git
cd analyse-statistique-engagement-mooc
```

### Structure du projet

```bash
analyse-statistique-engagement-mooc/
├── data/                    # Jeux de données bruts et nettoyés
├── LICENSE
├── notebook/                # Analyses en R (scripts RMarkdown)
├── rapport_mooc_effectuation.docx
├── README.md
└── references/              # Énoncé et articles de référence
```
## Analyses réalisées
### Préparation des données
- Fusion de 3 itérations du MOOC Effectuation (`usages.effec1-3`, `effect1-3.quest.compil`)
- Nettoyage et uniformisation des colonnes
- Création de variables synthétiques :
  - `videos_visionnees` : somme des vidéos regardées
  - `quizz_realises` : somme des quiz complétés
  - `HDI` : regroupement des catégories de développement humain

### Typologie des apprenants
Catégorisation selon l'engagement :
- **Completer** : Examen ou certificat obtenu
- **Disengaging Learner** : Quiz ou devoirs mais pas de certificat
- **Auditing Learner** : +6 vidéos mais pas d'activité évaluée
- **Bystander** : -6 vidéos et pas d'activité

### Analyses statistiques
- **Test du Chi²** et **V de Cramer** : lien entre Genre et HDI
- **ANOVA** : effet du Genre et HDI sur le visionnage de vidéos
- **Régression logistique** : prédiction de l'obtention du certificat
- **Régression de Poisson** : modélisation des données de comptage
- **Tests non paramétriques** : Wilcoxon, Kruskal-Wallis, Spearman

### Diagnostics et validation
- QQ-plots, analyse des résidus
- Validation des hypothèses des modèles
- Calcul d'erreurs (RMSE, MAE) pour les prédictions
## Résultats principaux
### Distribution des apprenants
- Bystander : 45.2%

- Auditing Learner : 28.7%

- Disengaging Learner : 18.1%

- Completer : 8.0%

### Relations significatives
- Lien faible mais significatif entre Genre et HDI (V de Cramer = 0.11)

- Effet significatif du HDI sur le nombre de vidéos visionnées

- Odd-ratio pour l'obtention du certificat : 1.32 pour HDI "TH" vs référence
## Références

- **[Énoncé du projet](./references/enonce_projet.pdf)**
- [Article "A Tale of Two MOOCs"](./references/a_tale_of_two_moocs.pdf)
## Auteur

[@naima-beck](https://www.github.com/naima-beck) - Cy Tech - Sciences-Po Saint-Germain-En-Laye - [2024/2025]


## License

Ce projet est réalisé dans un cadre académique. Les données sont fournies pour usage pédagogique.
Il est sous licence [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
![License](https://img.shields.io/badge/License-CC%20BY--NC--SA-blue.svg)
