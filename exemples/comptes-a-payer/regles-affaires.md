# Référentiel fictif et règles d'affaires

## Centres et alias — exemple seulement
| Centre | Alias textuel | Code | Adresse fictive |
|---|---|---|---|
| A | Centre A; Recherche Nord | CTR-A | 100 rue Exemple |
| B | Centre B; Laboratoire Est | CTR-B | 200 rue Exemple |
| C | Centre C; Administration Sud | CTR-C | 300 rue Exemple |
| D | Centre D; Services Ouest | CTR-D | 400 rue Exemple |

## Règles proposées à faire approuver
| ID | Critère | Traitement |
|---|---|---|
| R01 | Un seul code de centre reconnu, sans contradiction | Proposer ce centre |
| R02 | Nom ou alias exact reconnu dans courriel/PDF | Proposer ce centre |
| R03 | Adresse de facturation univoque validée dans référentiel | Proposer ce centre |
| R04 | Signaux de centres différents | Vérification manuelle |
| R05 | Aucun indice / document non lisible | Vérification manuelle |
| R06 | Plusieurs PDF reliés à différents centres | Vérification manuelle |
| R07 | Fournisseur connu sans autre indice | Pas de classification automatique |
| R08 | Centre confirmé après analyse complète | Déplacer le courriel dans le dossier autorisé |

## Règles d'implantation
- Inscrire les variantes orthographiques approuvées; éviter les correspondances de sous-chaînes trop larges.
- Tester les adresses partagées, les faux positifs et les correspondances partielles.
- Conserver version et date du référentiel.
- L'identification d'un centre **n'autorise pas** le paiement.
