# Cartographier un processus : AS-IS, TO-BE et BPMN

## Quel diagramme ?
- **AS-IS** : situation actuelle observée et validée, avec irritants et exceptions.
- **TO-BE** : processus cible après amélioration, avec responsables et contrôles.
- **Diagramme de flux** : représentation simple de décisions et activités.
- **Cartographie à couloirs** (*swimlanes*) : activités placées chez le rôle responsable.
- **BPMN 2.0** : notation standardisée pour processus, événements, activités, passerelles et flux.

## Démarche d'entrevue
Demander : qui déclenche le travail ? quelles entrées ? qui agit ? quel système ? quelle décision ? que se passe-t-il si l'information manque ? quelle sortie ? qui approuve ? où attend-on ?

## Symboles courants
| Élément | BPMN 2.0 | Signification |
|---|---|---|
| Événement de début/fin | Cercle | Départ / résultat |
| Tâche | Rectangle arrondi | Travail humain ou automatisé |
| Passerelle exclusive | Losange (X) | Une branche parmi plusieurs |
| Passerelle parallèle | Losange (+) | Branches simultanées |
| Flux de séquence | Flèche pleine | Ordre dans un même pool |
| Flux de message | Flèche en pointillés | Communication entre pools |
| Pool / lane | Conteneur / couloir | Participant / responsabilité |
| Objet de données | Icône document | Information utilisée ou produite |

**Important** : pour un BPMN strict, le **fournisseur externe** et l'**organisation** sont généralement deux *pools* distincts; on utilise un flux de message entre eux. Outlook, Power Automate et AI Builder peuvent être modélisés comme systèmes ou tâches de service dans les couloirs internes. Ne pas appeler « BPMN 2.0 conforme » un simple Mermaid flowchart à sous-graphes.

## Validation d'un AS-IS
- Chaque tâche a un responsable.
- Chaque décision a des conditions de sortie explicites.
- Les exceptions et reprises sont visibles.
- Les attentes et transferts interéquipes sont représentés.
- Les participants reconnaissent le travail réel.

## Validation d'un TO-BE
- Le propriétaire de chaque tâche est défini.
- Le chemin d'exception est praticable.
- Les données nécessaires à chaque décision existent.
- Les contrôles, accès, journaux et validations sont documentés.
- Les points de mesure sont placés sur le flux.

## Outils
- **Bizagi Modeler / Camunda Modeler** pour une vraie modélisation BPMN 2.0.
- **diagrams.net / Visio** pour une cartographie visuelle avec couloirs.
- **Mermaid** pour de rapides diagrammes texte versionnés dans GitHub, sans prétention de conformité BPMN.

Voir [gabarit de cartographie](../gabarits/03-cartographie-processus.md) et [exemple illustré](../exemples/comptes-a-payer/cartographies.md).
