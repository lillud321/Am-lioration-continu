# Étude de cas complète — Optimisation du cycle des factures fournisseurs (P2P)

> **Étude fictive**, inspirée d'une organisation multisite. Tous les chiffres, acteurs et décisions sont inventés pour l'apprentissage. Aucun diagnostic réel n'a été réalisé.

## Pourquoi ce cas ?
Il va beaucoup plus loin qu'un tri de courriels : le traitement d'une facture implique **achats, demandeurs, réception des biens/services, approbateurs, comptabilité, trésorerie et fournisseur**, avec contrôles de conformité, délais, exceptions et indicateurs BI.

### Contexte
Une organisation comporte **4 centres de coûts**, **3 000 factures par mois** et une équipe de comptes à payer. Certaines factures correspondent à des bons de commande (BC), d'autres à des achats sans BC. Les validations de service fait et les approbations circulent par courriel; la comptabilité doit parfois relancer les unités avant le paiement.

**Périmètre choisi** : de la **réception d'une facture** à son **paiement et rapprochement bancaire**, incluant réceptions, contrôles, approbations, enregistrement et traitement des exceptions. L'approvisionnement initial et la négociation des contrats sont hors périmètre, mais les informations de commande sont des entrées indispensables.

## Comment étudier ce cas
| Ordre | Document | Ce qu'il apprend |
|---|---|---|
| 1 | [Charte et SIPOC](01-define-charte-sipoc.md) | Cadrage, CTQ, parties prenantes, RACI |
| 2 | [Cartographie AS-IS et collecte](02-measure-as-is.md) | Couloirs, points d'attente, plan de mesure |
| 3 | [Analyse BI et causes](03-analyze-donnees-causes.md) | KPI, Pareto, 5 pourquoi, validation des hypothèses |
| 4 | [TO-BE et choix des solutions](04-improve-to-be.md) | Conception, priorisation, règles, contrôles |
| 5 | [Plan pilote et cahier de tests](05-pilote-tests.md) | UAT, critères d'acceptation, comparaison avant/après |
| 6 | [Contrôle et gouvernance](06-control-tableau-de-bord.md) | Dictionnaire KPI, alertes, plan de pérennisation |
| 7 | [Données fictives et questions](donnees-exercice.csv) | Jeu pour Excel / Power BI, exercices avec corrigé |

## Scénario de bout en bout
1. Fournisseur transmet la facture, avec référence de commande ou centre de coûts.
2. Comptes à payer contrôle les champs, le fournisseur, les doublons et les taxes.
3. Achats / réception confirme le BC et la réception du bien ou du service.
4. Responsable budgétaire approuve les écarts ou les achats sans BC.
5. Comptabilité saisit ou intègre la facture, puis effectue les rapprochements.
6. Trésorerie sélectionne les factures échues et effectue les paiements autorisés.
7. Comptabilité rapproche les décaissements et traite les rejets ou erreurs.
8. Le propriétaire du processus surveille la performance.

## Frontières et nuances
- Le **routage d'un courriel** n'est pas la même chose que l'**approbation d'une facture**.
- L'**enregistrement comptable** n'est pas la même chose que le **paiement**.
- L'**automatisation ne remplace pas la séparation des tâches** (création fournisseur, approbation, exécution du paiement).
- Une facture peut comporter plusieurs articles, centres et validations.
- Le processus cible respecte la politique d'achat, les règles de délégation et les contrôles de la direction financière; les seuils exacts doivent être validés localement.

## Résultat attendu de l'exercice
Produire un diagnostic factuel, un AS-IS validé, un TO-BE contrôlé, une simulation des impacts, un plan de déploiement et un tableau de bord permettant de savoir si les gains durent.

Ce dossier **ne représente pas une automatisation prête à déployer** : il sert de modèle pour la conduite d'un véritable projet d'amélioration continue.
