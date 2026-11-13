# A — ANALYZE | Mesures, Pareto et causes racines

## 1. Exemple de diagnostic mensuel — données entièrement fictives
| Mesure | Valeur AS-IS | Interprétation |
|---|---:|---|
| Factures reçues | 3 000 | Volume mensuel, non nombre de courriels |
| Avec reprise | 660 (22 %) | Au moins un retour ou correction |
| Médiane réception → prêt à payer | 14 jours | Hors délai jusqu'à l'échéance de paiement |
| P90 réception → prêt à payer | 31 jours | Longue traîne problématique |
| Traitement humain moyen (toutes factures) | 13 minutes | 650 h/mois (3 000 × 13 / 60) |
| Paiements à échéance | 2 610 / 3 000 (87 %) | Hypothèse : toutes ont une échéance définie |

**À ne pas confondre** : « 14 jours de délai » et « 13 minutes de travail humain ». La majeure partie du délai peut être de l'attente entre services.

## 2. Pareto des 660 reprises fictives
| Motif principal unique attribué à chaque facture reprise | Nombre | % des reprises | Cumul |
|---|---:|---:|---:|
| Attestation de réception/service fait absente | 264 | 40 % | 40 % |
| Mauvaise imputation / centre de coûts | 165 | 25 % | 65 % |
| Information fournisseur / facture incomplète | 99 | 15 % | 80 % |
| Écart entre facture et BC | 79 | 12 % | 92 % |
| Approbation / délégation non disponible | 53 | 8 % | 100 % |
| **Total** | **660** | **100 %** | |

**Précaution** : ce Pareto classe des motifs déclarés. Pour parler de « cause racine », il faut confirmer la causalité par vérifications.

## 3. Les 5 pourquoi — exemple hypothétique
**Symptôme :** facture bloquée en attente de service fait.
1. Pourquoi bloquée ? Le système ne trouve pas de réception confirmée.
2. Pourquoi pas de confirmation ? La personne responsable n'a pas validé l'étape.
3. Pourquoi ? La tâche est envoyée par courriel sans suivi centralisé.
4. Pourquoi ? Le BC, la réception et la facture ne sont pas liés à un statut partagé.
5. Pourquoi ? Les responsabilités et contrôles n'ont pas été définis dans un workflow de bout en bout.

**Hypothèse de cause racine** : absence de responsabilités et d'un suivi structuré des validations. **À vérifier** en analysant les journaux, en observant les équipes et en comparant les centres.

## 4. Comment vérifier réellement ?
| Hypothèse | Preuve recherchée | Analyse BI | Décision possible |
|---|---|---|---|
| Réceptions tardives expliquent les délais | Dates de livraison et de validation | Répartition P50/P90 par type de commande | Clarifier la confirmation de service |
| Imputations incorrectes génèrent reprises | Journal des corrections | Pareto par centre et fournisseur | Référentiel de codes et contrôles à la saisie |
| Absence d'approbateur substitut crée des attentes | Calendrier de délégations et horodatages | Délais par rôle et période d'absence | Règles de substitution approuvées |
| Fournisseurs sans BC génèrent davantage d'exceptions | Type de commande + motifs | Comparaison normalisée BC/sans BC | Politique de commandes / exceptions |

## 5. Indicateurs et formules
- Taux de reprise = **factures distinctes avec ≥1 reprise / factures admissibles × 100**.
- Taux de paiement à temps = **factures réglées à échéance / factures ayant une échéance exploitable × 100** (définir les factures encore ouvertes).
- Temps humain mensuel (h) = **Σ minutes de travail humain / 60**.
- Délai de prêt à payer = **date prête à payer − date de réception**, selon jours calendaires ou ouvrables explicitement déclarés.
- Pareto = nombre de dossiers par **motif principal exclusif** / nombre de dossiers repris.

## 6. Exemple de requête SQL conceptuelle
Adapter noms et fonctions à la base réelle; ne pas exécuter tel quel en production.

```sql
SELECT
    centre_id,
    COUNT(DISTINCT facture_id) AS factures,
    SUM(CASE WHEN nb_reprises > 0 THEN 1 ELSE 0 END) AS factures_avec_reprise,
    ROUND(100.0 * SUM(CASE WHEN nb_reprises > 0 THEN 1 ELSE 0 END)
         / NULLIF(COUNT(*), 0), 1) AS pct_reprises
FROM factures_kpi
WHERE date_reception >= '2026-09-01'
  AND date_reception < '2026-10-01'
GROUP BY centre_id;
```

> Hypothèse SQL : **une seule ligne par facture** dans `factures_kpi`. Sinon, agréger d'abord au grain facture.
