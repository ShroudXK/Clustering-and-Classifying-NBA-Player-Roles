# NBA Player Role Analysis

This project analyzes 2024–25 NBA player data to identify player roles and predict them from player attributes.

## What the notebook does

1. Cleans the data by removing missing weights, converting height to centimeters, and keeping each player's team record with the most games played.
2. Uses K-Means clustering on points, rebounds, and assists per game to group players into four roles: **Scoring Playmaker**, **Rebounding Big**, **Role Player**, and **Bench Player**.
3. Trains Decision Tree, K-Nearest Neighbors, and Random Forest classifiers to predict those roles from height, weight, age, and position. It compares the models with accuracy, classification reports, and confusion matrices.

## Run the project

Install the required Python packages:

```bash
pip install pandas matplotlib seaborn scikit-learn jupyter
```

Place `Project Code.ipynb` and `IS407 Final Project Data - 24-25 NBA Player Data.csv` in the same folder. Open the notebook with Jupyter and run its cells from top to bottom.

```bash
jupyter notebook "Project Code.ipynb"
```

The notebook displays the clustering plots, model results, and feature importance charts.

## Motivation

Traditional positions such as guard, forward, and center do not always describe what a player contributes on the court. This project explores whether basic game statistics can reveal different playing styles. It then asks a second question: can we estimate a player's statistical role using only their physical attributes, age, and listed position?

## Method

The notebook first checks missing values, converts heights to centimeters, and handles players with multiple team records by keeping the record with the most games played. It also plots correlations among numerical variables to explore the data.

For clustering, it standardizes points (`PTS`), rebounds (`REB`), and assists (`AST`) and plots the elbow curve for 1–10 clusters. The notebook uses four clusters and assigns each one a descriptive name based on its average statistics. Scatter plots show how the groups differ.

For classification, it uses height, weight, age, and the player's primary position as inputs. A 70/30 train/test split is used to compare a Decision Tree, K-Nearest Neighbors, and Random Forest. The notebook reports accuracy, classification reports, and confusion matrices; it also displays the Decision Tree and Random Forest feature importances.

## Limitations and future improvements

- **The role names are interpretations.** K-Means finds groups from three statistics; the labels are assigned afterward. The classification models predict these generated groups, so their accuracy does not show that the roles match expert judgments.
- **The features are limited.** Points, rebounds, and assists leave out defense, efficiency, and playing time. Adding these could produce more meaningful groups.
- **The data covers one season.** Testing on another NBA season would show whether the same roles and predictions hold up over time.
- **The evaluation could be stronger.** Cluster labels are created before the train/test split, and four clusters were selected from the elbow plot. Future work could compare cluster counts with silhouette scores, tune the classifiers with cross-validation, and evaluate against independently labeled player roles.
