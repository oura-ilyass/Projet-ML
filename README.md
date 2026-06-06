# Prédiction du Prix de l'Or par Machine Learning

Projet de machine learning supervisé visant à prédire le prix journalier de l'ETF GLD (Gold) à partir d'indicateurs financiers corrélés et de features temporelles construites, en comparant trois algorithmes de régression.

---

## Aperçu du projet

L'or est une matière première stratégique dont le cours est influencé par de nombreux facteurs macroéconomiques : inflation, taux de change, indices boursiers et prix du pétrole. Ce projet s'inscrit dans le cadre de la formation ISI 2025-2026 et met en œuvre un pipeline complet de machine learning — de l'exploration des données jusqu'à l'évaluation comparative des modèles — sur le dataset `gld_price_data.csv`.

---

## Structure du dépôt
├── Projet_ML.ipynb        # Notebook principal
├── gld_price_data.csv     # Dataset utilisé
---
## Prérequis

Python 3.8+ et les bibliothèques suivantes :

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## Comment exécuter le projet

1. Cloner le dépôt :
```bash
git clone https://github.com/oura-ilyass/Projet-ML.git
cd Projet-ML
```

2. Lancer le notebook :
```bash
jupyter notebook Projet_ML.ipynb
```

3. Exécuter les cellules dans l'ordre.

---

## Pipeline du projet

Étape               Description
--------------------------------------------------------------------------------
Exploration         Statistiques descriptives, valeurs manquantes, corrélations
Visualisation       Évolution du prix GLD, heatmap de corrélation, distribution
Feature Engineering GLD_lag1, GLD_lag5, GLD_ma7 (moyenne mobile 7 jours)
Prétraitement       Split chronologique 80/20, StandardScaler sans data leakage
Modélisation        Régression Linéaire, Random Forest, Gradient Boosting
Évaluation          MAE, RMSE, R² sur le jeu de test

---

## Résultats

=== Régression Linéaire === MAE : 0.67 → erreur moyenne en dollars RMSE : 0.90 → pénalise les grosses erreurs R² : 0.9657 → 1.0 = parfait, 0 = inutile, <0 = mauvais 
=== Random Forest === MAE : 1.13 → erreur moyenne en dollars RMSE : 1.43 → pénalise les grosses erreurs R² : 0.9130 → 1.0 = parfait, 0 = inutile, <0 = mauvais 
=== Gradient Boosting === MAE : 1.26 → erreur moyenne en dollars RMSE : 1.60 → pénalise les grosses erreurs R² : 0.8904 → 1.0 = parfait, 0 = inutile, <0 = mauvais

> La régression linéaire obtient les meilleures performances sur les trois métriques, avec une erreur moyenne inférieure à 1 dollar et un R² de 96.6 %.

---

## Conclusion

La régression linéaire s'est imposée comme le meilleur modèle, ce qui démontre que la relation entre les features temporelles et le prix de l'or à court terme est fondamentalement linéaire. Ce projet illustre l'importance de construire des features adaptées au domaine et de respecter les bonnes pratiques de modélisation sur les séries temporelles.

---

## Auteur

**Ilyass Ourahou**  
Filière : ISI 2025-2026
