# Méthode DMAIC — Guide pas à pas

DMAIC = **Define, Measure, Analyze, Improve, Control**. Convient particulièrement à un processus existant dont la performance doit être améliorée.

## 0. Choisir et prioriser
Sélectionner un problème réel, assez circonscrit pour être mesuré. Vérifier l'importance pour les clients internes, la fréquence, les risques et la faisabilité. Identifier un sponsor et un propriétaire du processus.

## D — Définir
**Questions** : quel irritant, pour qui, où débute et finit le processus, quel résultat attend-on ?
1. Rencontrer les personnes concernées (voix du client, VOC).
2. Rédiger le problème **sans imposer de solution**.
3. Fixer des objectifs SMART et les exclusions.
4. Faire un SIPOC rapide (fournisseurs, entrées, processus, sorties, clients).
5. Déterminer sponsor, pilote, exécutants et parties prenantes.

**Livrables** : [charte](../gabarits/01-charte-projet.md), [SIPOC](../gabarits/02-sipoc.md).
**Point de passage** : le sponsor confirme le problème, le périmètre et les critères de succès.

## M — Mesurer
1. Observer le travail réel, pas seulement la procédure écrite.
2. Dessiner le **AS-IS** avec les acteurs, décisions, exceptions et transferts.
3. Définir chaque KPI : formule, unité, période, source, limites.
4. Collecter un échantillon représentatif, avec volumes et cas atypiques.
5. Mesurer la situation de référence (*baseline*); vérifier la qualité des données.

**Livrables** : [cartographie](../gabarits/03-cartographie-processus.md), [plan de mesure](../gabarits/04-plan-mesure-kpi.md).
**Point de passage** : les acteurs approuvent le AS-IS et les mesures peuvent être reproduites.

## A — Analyser
1. Stratifier par centre, fournisseur, type de document, période.
2. Rechercher où s'accumulent files d'attente, retouches et erreurs.
3. Employer Pareto, 5 pourquoi ou Ishikawa pour formuler des hypothèses.
4. Tester ces hypothèses sur des observations ou données; ne pas confondre corrélation et cause.
5. Prioriser les causes validées selon leur contribution et leur contrôlabilité.

**Livrable** : [analyse des causes](../gabarits/05-analyse-causes.md).
**Point de passage** : les causes retenues sont appuyées par des preuves, pas par des impressions.

## I — Améliorer
1. Supprimer les activités sans valeur, simplifier les règles, clarifier les responsabilités.
2. Comparer plusieurs solutions, y compris **ne pas automatiser**.
3. Dessiner le **TO-BE**, documenter règles, contrôles et exceptions.
4. Évaluer sécurité, accès, licences, coûts, maintenance et impacts humains.
5. Tester sur un pilote restreint avec critères d'acceptation et retour arrière.
6. Comparer après / avant à périmètre et définition comparables.

**Livrables** : [sélection de solutions](../gabarits/06-solutions-pilote.md), TO-BE, [tests](../gabarits/07-tests-acceptation.md).
**Point de passage** : le pilote est démontré, les risques résiduels sont acceptés.

## C — Contrôler
1. Définir qui surveille chaque KPI et à quelle fréquence.
2. Mettre des alertes et seuils qui conduisent à une action explicite.
3. Documenter procédures, formation, accès, maintenance et escalades.
4. Faire une revue à 30/60/90 jours puis ajuster.
5. Transférer la responsabilité du projet au propriétaire du processus.

**Livrable** : [plan de contrôle](../gabarits/08-plan-controle.md).
**Point de passage** : un responsable permanent et une routine de suivi existent.

## Erreurs à éviter
- Commencer par « il nous faut de l'IA » plutôt que par le problème.
- Mesurer uniquement le temps machine et ignorer le temps humain de correction.
- Déployer sans traiter les factures ambiguës, multiples ou illisibles.
- Comparer des périodes non comparables.
- Confondre **courriel classé** et **facture comptabilisée/payée**.

Voir aussi [BPMN et cartographie](02-cartographie-bpmn.md), [KPI BI](03-indicateurs-bi.md) et [automatisation](05-automatisation.md).
