# D — DEFINE | Charte de projet, SIPOC et responsabilités

## 1. Charte complétée (fictive)

| Élément | Décision de projet |
|---|---|
| Nom | Réduire les délais et les reprises du cycle fournisseurs |
| Sponsor | Directrice des finances |
| Propriétaire du processus | Chef des comptes à payer |
| Équipe | Comptabilité, achats, trésorerie, deux représentants des centres, TI/BI |
| Client interne | Gestionnaires de centres, trésorerie, direction financière |
| Client externe | Fournisseurs |
| Déclencheur | Facture reçue par le canal autorisé |
| Fin | Paiement confirmé et rapproché, ou rejet documenté |
| Problème | Délais variables et retraitements liés à des données incomplètes, à la réception et aux validations |
| Référence fictive | Médiane 14 jours réception → prêt à payer; 22 % de dossiers avec reprise |
| Objectif SMART | En 4 mois, réduire la médiane à 8 jours et les reprises à 10 %, sans augmenter erreurs et paiements non autorisés |
| Hors périmètre | Sélection des fournisseurs, appels d'offres, négociation, création initiale des BC |
| Risques | Paiement en double, erreurs de taxes, contournement d'approbation, données sensibles |
| Validation requise | Sponsor + propriétaire du processus + TI/sécurité |

**Énoncé de problème sans solution présupposée** : « Les factures fournisseurs prennent du temps à franchir les validations, avec des reprises mesurables, ce qui nuit aux échéances et mobilise les employés. »

## 2. SIPOC
| Fournisseurs (S) | Entrées (I) | Processus (P) | Sorties (O) | Clients (C) |
|---|---|---|---|---|
| Fournisseurs | Facture, taxes, coordonnées, référence BC | Recevoir et valider | Facture admissible ou rejet motivé | Comptabilité, fournisseur |
| Achats | BC, conditions, fournisseur autorisé | Apparier BC / réception / facture | Écarts documentés | Centre, achats |
| Centre / réception | Confirmation de service fait, budget, imputation | Approuver ou escalader | Facture autorisée et imputée | Comptabilité, trésorerie |
| Comptabilité | Écritures et contrôles ERP | Comptabiliser et préparer paiement | Dette fournisseurs correcte | Trésorerie, direction |
| Trésorerie / banque | Calendrier, autorisations, relevé bancaire | Payer puis rapprocher | Paiement rapproché / exception | Fournisseur, audit |

## 3. Voix du client (VOC) → critères CTQ
| Besoin exprimé (exemple) | Mesure opérationnelle CTQ |
|---|---|
| « Je veux éviter les retards de paiement » | % payé au plus tard à l'échéance |
| « Je veux savoir qui doit agir » | % dossiers avec responsable attribué |
| « Pas de paiement en double » | Nombre de doublons payés (tolérance cible : zéro) |
| « Je ne veux pas approuver deux fois » | % factures avec reprise / réapprobation |
| « Je veux suivre mes factures » | Délai P90 et backlog par statut / centre |

## 4. RACI simplifié
| Activité | Comptes à payer | Centre / approbateur | Achats / réception | Trésorerie | Propriétaire |
|---|---|---|---|---|---|
| Contrôle de complétude | R | C | C | I | A |
| Attestation de service fait | I | A/R | R | I | C |
| Approbation budgétaire | C | A/R | C | I | I |
| Enregistrement comptable | R | C | I | I | A |
| Autorisation et exécution du paiement | I | I | I | A/R | C |
| Suivi des KPI | R | C | C | C | A |

La matrice est illustrative : en pratique, **séparer** préparation, approbation et exécution des paiements selon la politique et les accès de l'organisation.

## 5. Points de validation avec les équipes
- Quelle est la date de début officielle : réception de l'e-mail ou importation au système ?
- Quels cas sont « exception » : sans BC, sans réception, écart de prix, facture fiscale incomplète ?
- Qui peut bloquer et débloquer une facture ? Avec quelles preuves ?
- Que signifie « paiement à temps » si une facture est reçue après échéance ?
- Quelles données sont fiables pour mesurer les dates de chaque étape ?

**Livrable à faire approuver** : charte + SIPOC + critères CTQ avant de construire un flux.
