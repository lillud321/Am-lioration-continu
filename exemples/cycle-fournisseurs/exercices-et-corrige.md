# Exercices — Passer du cas à un véritable raisonnement BI

Travailler à partir de [donnees-exercice.csv](donnees-exercice.csv). **Le CSV n'est pas l'échantillon ayant servi aux chiffres mensuels de 3 000 factures** : il est un petit jeu d'entraînement fictif.

## Questions à faire soi-même
1. Calculer volume, % avec ≥1 reprise, moyenne et médiane du délai, temps actif total.
2. Comparer les factures **BC** et **Sans_BC** (temps, reprises, paiement à échéance). Ne pas conclure à une causalité.
3. Faire un Pareto de `motif_principal` **uniquement parmi les factures avec reprise**.
4. Dessiner un AS-IS à couloirs pour la réception, le contrôle, la validation et le paiement.
5. Choisir deux améliorations et justifier pourquoi elles s'attaquent aux causes mesurées.
6. Décrire trois risques de contrôle financier créés par une automatisation mal conçue.
7. Rédiger une charte et un plan pilote utilisant les [gabarits](../../gabarits/).

## Corrigé rapide (jeu fictif de 16 factures)
- Volume : **16** factures.
- Factures avec reprise : **8/16 = 50 %**.
- Temps actif total : **182 minutes**, soit **3 h 02**.
- Délai moyen : **10,94 jours** (175 / 16).
- Délai médian : **8,5 jours** (8e = 8; 9e = 9).
- Paiements à échéance : **11/16 = 68,75 %**.
- **Sans_BC** : 4 factures, toutes avec au moins une reprise; **BC** : 12 factures, 4 avec reprise. Échantillon trop petit et construit artificiellement pour inférer une causalité.
- Pareto (motifs parmi reprises) : Réception absente = 2, Approbation = 2, Imputation = 2, Écart BC = 1, Information fournisseur = 1.

> Les données d'exercice exagèrent volontairement les problèmes. Elles ne doivent pas servir de baseline et ne représentent pas les résultats fictifs globaux du cas.

## Étendre l'exercice
Pour un cas plus réaliste, simuler 12 semaines avec dates de réception, dates de service fait, approbations, lots de paiement, paiements partiels et réouvertures. Conserver **une table événements** distincte pour pouvoir construire un véritable tableau de bord de délais et de flux.
