# Business Intelligence appliquée à l'amélioration continue

## De la question d'affaires au KPI
1. Définir la décision à soutenir : « le tri automatique réduit-il le travail manuel sans augmenter les erreurs ? »
2. Définir le **grain** de données : un courriel, une facture ou un événement de traitement.
3. Distinguer **dimensions** (centre, fournisseur, canal, date) et **mesures** (durées, volumes, exceptions).
4. Spécifier sources, propriétaires, rafraîchissement, définitions et contrôles de qualité.
5. Créer une référence pré-changement; suivre tendances, segmentation et stabilité après changement.

## KPI recommandés
| KPI | Formule | Prudence |
|---|---|---|
| Volume de factures | Nombre distinct de factures reçues | Un courriel peut avoir plusieurs factures |
| Taux auto-classé | Courriels classés automatiquement / courriels admissibles | Définir *admissible* |
| Précision du classement | Classements automatiques corrects vérifiés / classements automatiques vérifiés | Mesurer sur échantillon contrôlé |
| Taux d'exception | Courriels dirigés en vérification / courriels analysés | Comparer par centre et fournisseur |
| Temps de tri humain | Somme des minutes de tri + corrections | Ne pas confondre avec durée totale |
| Délai de routage | Heure d'attribution - heure de réception | Médiane et P90, pas moyenne seule |
| Taux de reprise | Dossiers nécessitant une réaffectation / dossiers assignés | Vérifier les causes |
| Coût net | Temps humain x coût horaire chargé + licences + maintenance | Documenter hypothèses |

## Modèle de données minimal
**Messages** : message_id, date_reception, centre_propose, centre_confirme, source_classement, statut, date_routage.
**Factures** : facture_id, message_id, fournisseur_id, nombre_pages, type_pdf.
**Événements** : event_id, message_id, type_evenement, horodatage, acteur, résultat.

Les identifiants doivent être pseudonymisés si les données quittent le système autorisé. Prévoir les duplications et la conservation. Éviter de verser les corps de courriel et PDF dans Power BI sans justification.

## Tableau de bord : page 1
Cartes : volume reçu, taux auto-classé, précision vérifiée, taux d'exception, heures humaines.
Graphiques : tendance hebdomadaire, Pareto des causes d'exception, distribution par centre, délai P50/P90.
Tableau d'action : anomalies, responsable, date limite.

## Mini-exemple fictif
- 1 200 courriels admissibles / mois.
- 900 automatiquement classés, dont 45 erronés lors de la revue exhaustive : **75 % auto-classés** et **95 % de précision**.
- 300 exceptions manuelles.
- Il faut aussi compter le travail de correction des 45 erreurs; une « précision de 95 % » peut être inacceptable selon le risque.

Voir [plan de mesure](../gabarits/04-plan-mesure-kpi.md) et [jeu de données d'exemple](../exemples/comptes-a-payer/donnees-fictives.csv).
