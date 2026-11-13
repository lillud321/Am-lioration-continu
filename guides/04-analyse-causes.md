# Analyser les causes : ne pas confondre symptôme et cause

## 5 pourquoi
Partir d'un incident factuel, demander « pourquoi ? » jusqu'à trouver une cause vérifiable et actionnable. Il peut y avoir plusieurs branches; « cinq » n'est pas une obligation.

## Ishikawa (causes possibles)
Regrouper les hypothèses par **méthodes**, **personnes**, **systèmes**, **données/documents**, **environnement** et **mesures**. Faire participer les commis.

## Pareto
Compter les cas par cause (ex. nom de centre absent, PDF image, fournisseur multi-centres, information contradictoire). Trier en ordre décroissant pour prioriser les principaux irritants. Ne pas transformer automatiquement la catégorie dominante en « cause racine ».

## Vérification des hypothèses
| Hypothèse | Observation ou test | Décision |
|---|---|---|
| Noms de centre absents du courriel | Échantillon représentatif de messages | Confirmer / rejeter |
| PDF contenant adresse identifiable | Extraction sur documents fictifs puis échantillon autorisé | Confirmer / rejeter |
| Une même adresse correspond à plusieurs centres | Vérification du référentiel de centres | Corriger la règle |
| Les erreurs viennent des exceptions non traitées | Analyser historique de classement et reprises | Corriger l'escalade |

Une cause n'est considérée *validée* que lorsqu'il existe une preuve. Utiliser [le gabarit d'analyse](../gabarits/05-analyse-causes.md).
