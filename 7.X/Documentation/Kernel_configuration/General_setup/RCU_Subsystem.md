RCU Subsystem:

| Option                                                   | Valeur  | Description                                                                                   |
|----------------------------------------------------------|---------|-----------------------------------------------------------------------------------------------|
| Make expert-level adjustments to RCU configuration       | Off     | Effectue des ajustements avancés sur la configuration du RCU.                                 |
| Offload RCU callback processing from boot-selected CPUs  |         | Éprouve l'offloading du traitement des appels de rappel RCU des CPU sélectionnés à démarrage. |
| Offload RCU callback processing from all CPUs by default | [*]     | Défaut : Éprouve l'offloading du traitement des appels de rappel RCU de tous les CPU.         |
| RCU callback lazy invocation functionality               | [ ]     | Fonctionnalité d'appel de rappel RCU à l'exécution retardée.                                  |
| Turn RCU lazy invocation off by default                  | [ ]     | Défaut : Désactive l'appel de rappel RCU à l'exécution retardée.                              |
