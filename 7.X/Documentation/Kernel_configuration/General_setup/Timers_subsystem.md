Timers subsystem

| Option                                                        | Valeur  | Description                                                                                                                    |
|---------------------------------------------------------------|---------|--------------------------------------------------------------------------------------------------------------------------------|
| [Force user context tracking](https://github.com/MarcJaffre/Kernel/blob/main/7.X/Documentation/Kernel_configuration/General_setup/Timers_subsystem/Timer_tick_handling.md) | [ ]     | Forcer la traçabilité du contexte utilisateur, peut être nécessaire pour certains scénarios de surveillance ou d'audit.        |
| Old Idle dynticks config                                      | [ ]     | Configuration de l'ancien mode dynticks idle, peut être utilisé pour des paramètres historiques ou spécifiques.                |
| High Resolution Timer Support                                 | [*]     | Permet un support d'horloge avec une résolution élevée, améliorant la précision du temps en microsecondes.                     |
| Clocksource watchdog maximum allowable skew (in microseconds) | (125)   | Détermine la tolérance maximale de l'écart entre le chronomètre source et le système, ici 125 microsecondes.                   |
| Enable auxiliary POSIX clocks                                 | [ ]     | Activer les horloges auxiliaires POSIX, utile pour des applications nécessitant plusieurs horloges temporisées.                |
