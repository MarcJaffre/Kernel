--------------------------------------------------------------------------------------------------------
## I. Guide 
### A. Prompt
```
Quel est le meilleur paramètre pour un PC Ryzen 7 3700x sous Debian 12 :
```

#### 01. General Setup
Les paramètres de compilation sont configurés pour une installation standard de Debian 12, avec des options pour améliorer les performances et la sécurité.

Les avertissements ne sont pas considérés comme des erreurs, et les pilotes inutiles ne sont pas compilés.

Les en-têtes de test UAPI et les informations de version personnalisées ne sont pas nécessaires.

Le mode de compression du noyau est configuré pour utiliser zstd, et le chemin d'initialisation par défaut est /sbin/init.

Les options de sécurité et de performances sont activées, notamment l'audit, la planification de cœur pour SMT et l'attribution de placement de mémoire pour le planificateur NUMA.

Les options de débogage et de profilage sont désactivées, sauf pour l'interface de débogage d'indexation printk.

```
- 01. Compile also drivers which will not load : <Boolean>
- 02. Compile the kernel with warnings as errors : <Boolean>
- 03. Compile test UAPI headers : <Boolean>
- 04. Local Version - apprend to kernel release: <String>
- 05. Automatically apprend version information to the version string: <Boolean>
- 06. Build ID Salt : <String>
- 07. Kernel compression mode: <gzip, bzip, zstd, none>
- 08. Default init path: <string>
- 09. Default Hostname: <string>
- 10. System V IPC: <Boolean>
- 11. POSIX Message queues : <Boolean>
- 12. General notification queue : <Boolean>
- 13. Enable process_vm_readv/writev_syscalls : <Boolean>
- 14. uselib syscall (for libc5 and earlier) : <Boolean>
- 15. Auditing support : <Boolean>
- 16. Preemption Model : <Boolean>
- 17. Preemption behaviour defined on boot : <Boolean>
- 18. Core Scheduling for SMT : <Boolean>
- 19. CPU Isolation : <Boolean>
- 20. Kernel .config support : <Boolean>
- 21. Enable kernel headers throught /sys/kernel/kheaders.tar.xz : <Boolean>
- 22. Kernel log buffer size : <Boolean>
- 23. CPU Kernel log buffer size contribution : <Boolean>
- 24. Printk indexing debugfs interface : <Boolean>
- 25. Memory placement award NUMA scheduler : <Boolean>
- 26. Checkpoint/restore support : <Boolean>
- 27. Automatic process group scheduling : <number>
- 28. Kernel -> user space relay support : <number>
- 29. Initial Ram filesystem and RAM disk (initramfs/initrd) support : <string>
- 30. Boot config support : <Boolean>
- 31. Preserve cpio archive mtimes in intiramfs : <Boolean>
- 32. Compiler optimisation level : <Boolean>
- 33. Profiling support : <Boolean>
```

| Nom du paramètre                                  | Valeur     | Commentaire                                                                                |
| -----                                             | -----      | -----                                                                                      |
| 01. Compile also drivers which will not load      | false      | Sauf si vous avez des besoins spécifiques                                                  |
| 02. Compile the kernel with warnings as errors    | false      | Pour éviter les erreurs de compilation inutiles                                            |
| 03. Compile test UAPI headers                     | false      | Sauf si vous développez des applications qui utilisent ces headers                         |
| 04. Local Version - append to kernel release      | <Vide>     | Sauf si vous voulez personnaliser la version du noyau                                      |
| 05. Automatically apprend version information ... | true       | Pour avoir des informations de version précises                                            |
| 06. Build ID Salt                                 | <vide>     | Sauf si vous voulez personnaliser l'ID de build                                            |
| 07. Kernel compression mode                       | zstd       | Pour une compression efficace                                                              |
| 08. Default init path                             | /sbin/init | Chemin par défaut pour l'initialisation du système                                         |
| 09. Default Hostname                              | Debian     | Nom d'hôte par défaut, mais vous pouvez le personnaliser                                   |
| 10. System V IPC                                  | true       | Pour supporter les IPC de System V                                                         |
| 11. POSIX Message queues                          | true       | Pour supporter les files d'attente de messages POSIX)                                      |
| 12. General notification queue                    | true       | Pour supporter les notifications générales                                                 |
| 13. Enable process_vm_readv/writev_syscalls       | true       | Pour supporter les appels système de lecture et d'écriture de processus                    |
| 14. uselib syscall (for libc5 and earlier)        | false      | Sauf si vous utilisez une version de libc antérieure à la 5                                |
| 15. Auditing support                              | true       | Pour supporter l'audit du système                                                          |
| 16. Preemption Model                              | Desktop    | Pour un modèle de préemption adapté aux bureaux                                            |
| 17. Preemption behaviour defined on boot          | true       | Pour définir le comportement de préemption au démarrage                                    |
| 18. Core Scheduling for SMT                       | true       | Pour supporter la planification des cœurs pour SMT                                         |
| 19. CPU Isolation                                 | false*     | Sauf si vous voulez isoler des CPU spécifiques                                             |
| 20. Kernel .config support                        | true       | Pour supporter la configuration du noyau                                                   |
| 21. Enable kernel headers through .....           | true       | Pour supporter les headers du noyau                                                        |
| 22. Kernel log buffer size                        | 16         | Taille par défaut du tampon de journalisation du noyau                                     |
| 23. CPU Kernel log buffer size contribution       | 8          | Contribution par défaut de la taille du tampon de journalisation du noyau pour chaque CPU  |
| 24. Printk indexing debugfs interface             | true       | Pour supporter l'interface de débogage de printk                                           |
| 25. Memory placement award NUMA scheduler         | true       | Pour supporter la planification NUMA aware                                                 |
| 26. Checkpoint/restore support                    | true       | Pour supporter la sauvegarde et la restauration des processus                              |
| 27. Automatic process group scheduling            | 2          | Planification automatique des groupes de processus                                         |
| 28. Kernel -> user space relay support            | 2          | Pupport de relais entre le noyau et l'espace utilisateur                                   |
| 29. Initial Ram filesystem and RAM disk ....      | initramfs  | Support de l'initramfs                                                                     |
| 30. Boot config support                           | true       | Pour supporter la configuration du démarrage                                               |
| 31. Preserve cpio archive mtimes in initramfs     | true       | Pour conserver les dates de modification des archives cpio dans l'initramfs                |
| 32. Compiler optimisation level                   | -O2        | Niveau d'optimisation du compilateur                                                       |
| 33. Profiling support                             | true       | Pour supporter le profilage du système                                                     |

<br />

#### 02. IRQ Sub-System
Ces paramètres devraient fournir une bonne base pour la gestion des interruptions, mais n'oubliez pas de les ajuster en fonction de vos besoins spécifiques.

```
1. Supportsparse irq numbering : <Boolean>
2. Expose irq internals in debugfs : <Boolean>
```

| Nom du paramètre                    | Valeur | Commentaire                                                                                                          |
| -----                               | -----  | -----                                                                                                                |
| 1. Supportsparse irq numbering      | True   | Cela permet d'optimiser la gestion des interruptions (IRQ) et peut améliorer les performances.                       |
| 2. Expose irq internals in debugfs  | False  | Cela n'est généralement pas nécessaire pour un usage normal et peut potentiellement créer des problèmes de sécurité. |

<br />

#### 03. Timers subsystem
Ces paramètres devraient fournir une bonne base pour la gestion des timers et des interruptions, mais n'oubliez pas de les ajuster en fonction de vos besoins spécifiques.

```
1. Timer tick handling : <Boolean>
2. Force user context tracking : <Boolean>
3. Old Idle dynticks config : <Boolean>
4. High Resolution Timer Support : <Boolean>
5. ClockSource Watchdog maximum allowable skew (in ms) : <Number>
```

| Nom du paramètre                                  | Valeur | Commentaire                                                                                                      |
| -----                                             | ----   | -----                                                                                                            |
| 1. Timer tick handling                            | False  | Cela permet de gérer les ticks de l'horloge système de manière plus efficace.                                    |
| 2. Force user context tracking                    | False  | Cela n'est généralement pas nécessaire pour un usage normal et peut créer des problèmes de performances.         |
| 3. Old Idle dynticks config                       | False  | Cela est généralement déprécié et non recommandé.                                                                |
| 4. High Resolution Timer Suppor                   | True   | Cela permet d'améliorer la précision des timers système.                                                         |
| 5. ClockSource Watchdog maximum allowable skew    | 100    | Cela dépend de vos besoins spécifiques, mais une valeur de 100 ms est généralement considérée comme raisonnable. |

<br />

#### 04. BPF subsystem
Ces paramètres devraient fournir une bonne base pour la gestion des fonctionnalités BPF*, mais n'oubliez pas de les ajuster en fonction de vos besoins spécifiques.

BPF : Mécanisme de filtrage et de traitement de paquets de réseau pour exécuter des programmes de filtrage et de traitement de paquets à l'intérieur du noyau du système d'exploitation.


```
1. Enable bpf() system call : <Boolean>
2. Enable BPF Just In Time compiler : <Boolean>
3. Permanently enable BPF JIT and remove BPF interpreter : <Boolean>
4. Disable unprivileged BPF by default : <Boolean>
5. Enable BPF LSM Instrumentation : <Boolean>
```



| Nom du paramètre                                          | Valeur | Commentaire                                                                                                                        |
| -----                                                     | -----  | -----                                                                                                                              |
| 1. Enable bpf() system call                               | True   | Cela permet d'activer l'appel système bpf() qui est utilisé pour les opérations de filtrage de paquets.                            |
| 2. Enable BPF Just In Time compiler                       | True   | Cela permet d'améliorer les performances des programmes utilisant BPF en compilant le code BPF en code machine à la volée.         |
| 3. Permanently enable BPF JIT and remove BPF interpreter  | False  | Cela n'est généralement pas recommandé car il peut créer des problèmes de compatibilité avec les anciens programmes utilisant BPF. |
| 4. Disable unprivileged BPF by default                    | False  | Cela permet aux utilisateurs non privilégiés d'utiliser BPF, ce qui est généralement souhaitable pour les applications de réseau.  |
| 5. Enable BPF LSM Instrumentation                         | True   | Cela permet d'activer l'instrumentation de sécurité BPF pour améliorer la visibilité et la sécurité du système.                    |

<br />

#### 05. CPU task time and stats accounting
Ces options sont liées à la comptabilité des tâches et des statistiques.
```
1. Cputime accounting : <Boolean>
2. Fine granularity task level IRQ time accounting : <Boolean>
3. BSD Process Accounting : <Boolean>
4. Export task/process statistics through netlink : <Boolean>
5. Pressure stall information tracking : <Boolean>
```

| Nom du paramètre                                    | Valeur | Commentaire                                                                 |
| -----                                               | -----  | -----                                                                       |
| 1. Cputime accounting                               | False  | Comptabilité du temps CPU                                                   |
| 2. Fine granularity task level IRQ time accounting  | False  | Comptabilité du temps d'interruption de niveau de tâche à granularité fine  |
| 3. BSD Process Accounting                           | False  | Comptabilité des processus BSD                                              |
| 4. Export task/process statistics through netlink   | False  | Exportation de statistiques de tâches/processus via netlink                 |
| 5. Pressure stall information tracking              | False  | Suivi des informations de blocage de pression                               |

<br />

#### 06. RCU Subsystem
RCU (Read-Copy Update) est un mécanisme de synchronisation dans le noyau Linux. Ces options permettent un contrôle fin de la comportement de RCU.
```
1. Make expert-level adjustments to RCU : <Boolean>
2. Configuration Force selection of TASKS_RCU : <Boolean>
3. Force selection of Tasks Rude RCU : <Boolean>
4. Force selection of Tasks Trace RCU : <Boolean>
4A. Tree-based hierarchical RCU fanout value : <Boolean>
4B. Tree-based hierarchical RCU leaf-level fanout value : <Boolean>
5. Enable RCU priority boosting : <Boolean>
6. Offload RCU callback processing from boot-selected CPUs : <Boolean>
7. Tasks Trace RCU readers use memory barriers in user and idle : <Boolean>
8. RCU callback lazy invocation functionality (NEW) : <Boolean>
9. RCU callback-batch backup time check : <Boolean>
```

| Nom du paramètre                                                 | Valeur | Commentaire                                                                                        |
| -----                                                            | -----  | -----                                                                                              |
| 1. Make expert-level adjustments to RCU                          | False  | Sauf si vous êtes un expert et que vous savez ce que vous faites                                   |
| 2. Configuration Force selection of TASKS_RCU                    | False  | Configuration Force la sélection de TASKS_RCU                                                      |
| 3. Force selection of Tasks Rude RCU                             | False  | Force la sélection de Tasks Rude RCU                                                               |
| -----                                                            | -----  | -----                                                                                              |
| 4. Force selection of Tasks Trace RCU                            | False  | Force la sélection de Tasks Trace RCU                                                              |
| 4A. Tree-based hierarchical RCU fanout value                     | False  | Valeur de fanout hiérarchique RCU basée sur l'arbre                                                |
| 4B. Tree-based hierarchical RCU leaf-level fanout value          | False  | Valeur de fanout de niveau feuille hiérarchique RCU basée sur l'arbre                              |
| -----                                                            | -----  | -----                                                                                              |
| 5. Enable RCU priority boosting                                  | True   | Peut améliorer la réactivité du système                                                            |
| 6. Offload RCU callback processing from boot-selected CPUs       | True   | Peut améliorer les performances du système                                                         |
| 7. Tasks Trace RCU readers use memory barriers in user and idle  | False  | Les lecteurs de tâches Trace RCU utilisent des barrières de mémoire en mode utilisateur et inactif |
| 8. RCU callback lazy invocation functionality (NEW)              | False  | Fonctionnalité d'invocation lazy des rappels RCU                                                   |
| 9. RCU callback-batch backup time check                          | False  | Vérification de la sauvegarde du temps de traitement des rappels RCU                               |


<br />

#### 07. Scheduler features
```
1. Enable utilization clamping for RT/FAIR tasks
2. Number of supported utilization clamp buckets
```

<br />

#### 08. Control Group Support
```
01. Favor dynamic modification latency reduction by default
02. Memory controller
03. IO controller
04. Utilization clamping per group of tasks
05. PIDs controller
06. RDMA controller
07. Freezer controller
08. HugeTLB controller
09. Cpuset controller
10. Include legacy /proc//cpuset file
11. Device controller
12. Simple CPU accounting controller
13. Perf controller
14. Support for eBPF programs attached to cgroups
15. Misc resource controller
16. Debug controller
```

<br />

#### 09. Namespaces Support
```
```

<br />

#### 10. Configure standard kernel features
```
```

<br />

#### 11. Kernel Performance Events And Counters
```
```

<br />

#### 12. Kexec and crash features
