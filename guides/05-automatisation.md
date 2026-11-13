# Quand automatiser un processus ?

## Ordre recommandé
1. **Éliminer** les tâches inutiles.
2. **Standardiser** noms, codes, champs et responsabilités.
3. **Simplifier** les contrôles et règles.
4. **Automatiser** les étapes stables, fréquentes et répétitives.
5. **Surveiller** les exceptions et la performance.

## Choisir une solution
| Option | Quand l'envisager | Risque à évaluer |
|---|---|---|
| Règles Outlook | Critères simples présents dans le message | Ne lit pas automatiquement tout le contenu PDF |
| Power Automate cloud | Intégration Outlook / dossiers / règles | Licences, permissions, limites connecteur |
| OCR / AI Builder | PDF numérisés ou texte PDF à extraire | Coût, fiabilité, gouvernance des données |
| Power Automate Desktop | Extraction locale et logiciels Windows | Ordinateur/exécution, orchestration et licences |
| Formulaire fournisseur | Champ « centre » obligatoire | Adoption fournisseur, changement d'habitude |
| Tri manuel standardisé | Faible volume ou risque élevé | Charge de travail, temps de traitement |

## Architecture de décision pour les factures
- Règles explicites, référentiel de centres et priorité documentée.
- Ne pas supposer qu'un fournisseur correspond à un seul centre.
- Si centres multiples, documents illisibles ou signaux contradictoires : **vérification manuelle**.
- Déplacer un courriel seulement après avoir évalué toutes ses pièces jointes.
- Journaliser règle appliquée, centre proposé, confiance ou motif d'exception, résultat et horodatage.
- Tester la sécurité des accès à la boîte partagée et aux services OCR avec les TI.

## Déploiement prudent
Commencer avec données fictives, mesurer les résultats, faire valider par les commis, déployer progressivement et conserver un retour arrière. Le coût doit inclure licences, OCR, correction humaine et maintenance.

Voir [cas complet](../exemples/comptes-a-payer/README.md).
