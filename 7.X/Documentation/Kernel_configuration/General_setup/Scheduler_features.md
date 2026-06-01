Scheduler features

| Option                                                               | Valeur | Description                                                                                   |
|----------------------------------------------------------------------|--------|-----------------------------------------------------------------------------------------------|
| CpuTime Accounting (Full dynticks CPU time accounting)               |  --->  |                                                                                               |
| Fine granularity task level IRQ time accounting                      |  [ ]   | Permet un granularité fine du temps d'IRQ au niveau de la tâche.                              |
| BSD Process Accounting (DEPRECATED)                                  |  [*]   | Comptage de processus basé sur BSD, obsolète.                                                 |
| BSD Process Accounting version 3 file format                         |  [*]   | Format de fichier pour le comptage de processus BSD v3.                                       |
| Export task/process statistics through netlink                       |  [*]   | Exporte les statistiques des tâches/processus via netlink.                                    |
| Enable per-task delay accounting                                     |  [*]   | Active l'enregistrement du retard par tâche.                                                  |
| Enable extended accounting over taskstats                            |  [*]   | Active un comptage étendu au-dessus de taskstats.                                             |
| Enable per-task storage I/O accounting                               |  [*]   | Active le comptage de stockage d'entrée/sortie par tâche.                                     |
| Pressure stall information tracking                                  |  [ ]   | Suivi des informations sur la pression et les temps d'inactivité (non coeur).                 |
| Require boot parameter to enable pressure stall information tracking |  [ ]   | Requiert un paramètre de démarrage pour activer le suivi des informations de pression.        |
