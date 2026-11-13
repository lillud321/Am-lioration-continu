# Cartographies du processus — exemples fictifs

## AS-IS (état actuel hypothétique)

```mermaid
flowchart LR
  A([Facture reçue]) --> B[Ouvrir courriel]
  B --> C[Lire courriel et PDF]
  C --> D{Centre identifiable ?}
  D -->|Oui| E[Attribuer à une commis]
  D -->|Non| F[Demander précision]
  F --> C
  E --> G([Facture orientée])
```

## TO-BE (état cible)

```mermaid
flowchart LR
  A([Courriel reçu]) --> B[Lire objet et corps]
  B --> C[Analyser PDF selon règles approuvées]
  C --> D[Consolider les indices par centre]
  D --> E{Un centre sans contradiction ?}
  E -->|Oui| F[Classer dans dossier du centre]
  E -->|Non| G[Vérification manuelle]
  F --> H([Routage terminé])
  G --> H
```

## Version à couloirs — esquisse Mermaid

```mermaid
flowchart TB
  subgraph Fournisseur
    A([Transmettre facture])
  end
  subgraph Outlook
    B[Recevoir le courriel dans la boîte partagée]
    H[Déplacer vers le dossier choisi]
  end
  subgraph Automatisation
    C[Analyser message et PDF]
    D[Appliquer les règles de correspondance]
    E{Un seul centre confirmé ?}
  end
  subgraph Commis
    F[Traiter facture attribuée]
    G[Vérifier et affecter manuellement]
    I([Routage terminé])
  end
  A --> B --> C --> D --> E
  E -->|Oui| H --> F --> I
  E -->|Non| G --> F
```

> Ce dernier est une **cartographie fonctionnelle à couloirs**, pas un fichier BPMN 2.0 conforme. Pour une carte de processus normative, réaliser dans Bizagi ou Camunda deux pools (Fournisseur, Organisation), des lanes (Commis, Système) et des flux de message entre pools.
