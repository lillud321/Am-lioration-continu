# Cas pédagogique fictif — Classement des factures reçues par courriel

> Toutes les organisations, les données et les résultats sont fictifs. Il ne s'agit pas de mesures réelles de l'organisation de l'utilisateur.

## Contexte
Une boîte Outlook Microsoft 365 commune reçoit les factures fournisseurs. Quatre commis prennent chacune en charge un centre (A, B, C, D). Le tri repose partiellement sur la lecture manuelle du courriel et des pièces jointes PDF.

## D — Define
**Problème** : la classification manuelle sollicite du temps et peut produire des transferts incorrects ou des retards.
**But du projet** : vérifier si un tri fondé sur des règles et, si nécessaire, une extraction PDF réduit l'effort de routage **sans détériorer la qualité**.
**Périmètre** : réception → attribution à la commis. **Exclusions** : saisie comptable, approbation, paiement.
**Acteurs** : fournisseur, responsable de la boîte, commis A–D, TI, propriétaire du processus.

## M — Measure
Exemple de paramètres **hypothétiques** : 1 200 courriels admissibles/mois, 2,5 minutes de tri manuel moyen, soit 50 heures/mois avant corrections. Les vraies valeurs doivent être relevées.
Mesurer : temps humain par courriel, délai réception-attribution, volume par centre, taux d'erreur, taux d'exception, reprises.

## A — Analyze
Hypothèses à confirmer :
- Certains messages ne mentionnent pas le centre dans leur objet ni leur corps.
- Le PDF contient parfois un nom de destinataire, une adresse ou un code de centre.
- Certains fournisseurs desservent plusieurs centres : **ne pas classer sur l'expéditeur seul**.
- Les documents multiples et contradictoires demandent un contrôle spécifique.

Valider les hypothèses sur un échantillon autorisé et représentatif, stratifié par fournisseur et centre.

## I — Improve
1. Créer un référentiel des noms, alias, adresses et codes des centres.
2. Détecter un centre avec les données du message; analyser les pièces jointes pertinentes suivant les règles approuvées.
3. Comparer **tous les indices** avant de déplacer.
4. **Un centre confirmé sans contradiction** → dossier du centre.
5. **Aucun centre, centres contradictoires ou PDF illisible** → vérification manuelle.
6. Journaliser la règle, le résultat, le moment et les exceptions.
7. Tester dans une boîte de test avec de faux documents; valider licences, accès et traitement des PDF avec TI.

### Choix technologique possible
- Outlook + Power Automate pour réception, règles et classement.
- Pour les PDF : OCR/AI Builder ou extracteur de texte approuvé, selon licences et type de PDF.
- Une vraie validation de faisabilité nécessite de tester les connecteurs et les permissions dans le tenant Microsoft 365.

## C — Control
Tableau de bord : volume, précision du classement (vérifiée), taux d'exceptions, temps humain total (y compris corrections), P90 délai de routage.
Définir le responsable de l'examen des exceptions, la procédure d'arrêt du flux et les revues 30/60/90 jours.

## Livrables du cas
- [Cartographies AS-IS / TO-BE](cartographies.md)
- [Règles d'affaires fictives](regles-affaires.md)
- [Cas de test](tests.md)
- [Petit jeu de données fictives](donnees-fictives.csv)

**Attention** : le routage du courriel ne prouve ni la réception comptable, ni l'approbation, ni le paiement de la facture.
