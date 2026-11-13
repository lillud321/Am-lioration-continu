# I — IMPROVE | Plan pilote, tests et mesure des gains

## 1. Pilote fictif
- **Durée** : 4 semaines.
- **Périmètre** : 1 centre de coûts, 300 factures admissibles.
- **Solution** : champs obligatoires, référence BC/réception et statut d'attente avec responsable.
- **Comparateur** : période préalable de 4 semaines, même centre et même types de factures, avec ajustement si volumes/saisonnalité différents.
- **Protection** : pas de paiement automatiquement autorisé par le pilote; environnement de test pour les intégrations.
- **Validation** : propriétaire du processus, comptabilité, achats, TI et trésorerie.

## 2. Critères d'acceptation proposés
| Dimension | Critère hypothétique |
|---|---|
| Délai | Médiane réception → prêt à payer ≤ 8 jours |
| Reprises | ≤ 10 % des factures pilotes |
| Qualité | 0 paiement sans autorisation |
| Doublons | 0 doublon payé |
| Suivi | ≥ 95 % des exceptions avec propriétaire et motif |
| Traçabilité | 100 % des approbations vérifiées dans les journaux |

Les critères doivent être validés par l'organisation; les deux objectifs « zéro » concernent des erreurs critiques observées, non une garantie statistique sur tous les cas futurs.

## 3. Cahier de tests UAT
| Test | Situation | Résultat attendu |
|---|---|---|
| T01 | Facture complète avec BC et service reçu | Appariement puis contrôle et comptabilisation |
| T02 | Facture sans code de centre | Demande de correction, responsable assigné |
| T03 | Quantité facturée supérieure à réception | Blocage, exception pour achats/réception |
| T04 | Prix supérieur à BC hors tolérance | Exception à approuver selon délégation |
| T05 | Même facture soumise deux fois | Doublon suspect bloqué et revu |
| T06 | Facture sans BC | Circuit dérogatoire, aucune approbation implicite |
| T07 | Approbateur en congé | Substitution autorisée et tracée |
| T08 | Paiement rejeté par banque | Statut rejet et exception de trésorerie |
| T09 | Facture multi-centres | Imputations validées sans double comptage |
| T10 | Note de crédit liée à facture | Traitement distinct, rapprochement correct |
| T11 | Workflow indisponible | Pas de perte de facture, file d'erreurs |
| T12 | Utilisateur sans privilège | Accès refusé, journalisé |

## 4. Comparaison avant / après — entièrement fictive
| KPI | Avant | Après pilote | Écart |
|---|---:|---:|---:|
| Médiane prêt à payer | 14 jours | 8 jours | -6 jours (-42,9 %) |
| Reprises | 22 % | 9 % | -13 points |
| Temps actif moyen | 13 min | 9 min | -4 min (-30,8 %) |
| Factures payées à échéance | 87 % | 93 % | +6 points |
| Factures sans approbation valide | 0 | 0 | Aucun incident observé |

**Projection de capacité théorique** : 3 000 factures × (13−9) minutes / 60 = **200 h/mois** économisées *si* les effets se maintiennent, que le mix de factures est comparable et que ces temps comprennent les exceptions et corrections. Ce n'est **pas une économie salariale réalisée** : les coûts de licences, formation, support et réallocation des tâches restent à évaluer.

## 5. Décision de déploiement
- [ ] Critères d'acceptation observés et signés
- [ ] Analyse des incidents / cas non couverts
- [ ] Confirmation de conformité et contrôles financiers
- [ ] Plan de reprise et arrêt d'urgence
- [ ] Coûts complets et capacité de soutien
- [ ] Communication, documentation et formation
- [ ] Propriétaire et calendrier de déploiement désignés
