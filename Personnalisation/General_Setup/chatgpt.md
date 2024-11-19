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
- 16. KUnit test for kernel/time functions: <Boolean> <======================================
- 17. Preemption Model : <Boolean>
- 18. Preemption behaviour defined on boot : <Boolean>
- 19. Core Scheduling for SMT : <Boolean>
- 20. CPU Isolation : <Boolean>
- 21. Kernel .config support : <Boolean>
- 22. Enable kernel headers throught /sys/kernel/kheaders.tar.xz : <Boolean>
- 23. Kernel log buffer size : <Boolean>
- 24. CPU Kernel log buffer size contribution : <Boolean>
- 25. Printk indexing debugfs interface : <Boolean>
- 26. Memory placement award NUMA scheduler : <Boolean>
- 27. Checkpoint/restore support : <Boolean>
- 28. Automatic process group scheduling : <boolean>
- 29. Kernel -> user space relay support : <boolean>
- 30. Initial Ram filesystem and RAM disk (initramfs/initrd) support : <string>
- 31. Boot config support : <Boolean>
- 32. Preserve cpio archive mtimes in intiramfs : <Boolean>
- 33. Compiler optimisation level : <Boolean>
- 34. Profiling support : <Boolean>
```

| Nom du paramètre                                  | Valeur     | Commentaire                                                                                |
| -----                                             | -----      | -----                                                                                      |
| 01. Compile also drivers which will not load      | False      | Sauf si vous avez des besoins spécifiques                                                  |
| 02. Compile the kernel with warnings as errors    | False      | Pour éviter les erreurs de compilation inutiles                                            |
| 03. Compile test UAPI headers                     | False      | Sauf si vous développez des applications qui utilisent ces headers                         |
| 04. Local Version - append to kernel release      | <Vide>     | Sauf si vous voulez personnaliser la version du noyau                                      |
| 05. Automatically apprend version information ... | True       | Pour avoir des informations de version précises                                            |
| 06. Build ID Salt                                 | <vide>     | Sauf si vous voulez personnaliser l'ID de build                                            |
| 07. Kernel compression mode                       | zstd       | Pour une compression efficace                                                              |
| 08. Default init path                             | /sbin/init | Chemin par défaut pour l'initialisation du système                                         |
| 09. Default Hostname                              | Debian     | Nom d'hôte par défaut, mais vous pouvez le personnaliser                                   |
| 10. System V IPC                                  | True       | Pour supporter les IPC de System V                                                         |
| 11. POSIX Message queues                          | True       | Pour supporter les files d'attente de messages POSIX)                                      |
| 12. General notification queue                    | True       | Pour supporter les notifications générales                                                 |
| 13. Enable process_vm_readv/writev_syscalls       | True       | Pour supporter les appels système de lecture et d'écriture de processus                    |
| 14. uselib syscall (for libc5 and earlier)        | False      | Sauf si vous utilisez une version de libc antérieure à la 5                                |
| 15. Auditing support                              | True       | Pour supporter l'audit du système                                                          |
| 16. KUnit test for kernel/time functions          | ------     | INCOMPLET !!!!                                                                             |
| 17. Preemption Model                              | Desktop    | Pour un modèle de préemption adapté aux bureaux                                            |
| 18. Preemption behaviour defined on boot          | True       | Pour définir le comportement de préemption au démarrage                                    |
| 19. Core Scheduling for SMT                       | True       | Pour supporter la planification des cœurs pour SMT                                         |
| 20. CPU Isolation                                 | ------     | Sauf si vous voulez isoler des CPU spécifiques                                             |
| 21. Kernel .config support                        | True       | Pour supporter la configuration du noyau                                                   |
| 22. Enable kernel headers through .....           | True       | Pour supporter les headers du noyau                                                        |
| 23. Kernel log buffer size                        | 16         | Taille par défaut du tampon de journalisation du noyau                                     |
| 24. CPU Kernel log buffer size contribution       | 8          | Contribution par défaut de la taille du tampon de journalisation du noyau pour chaque CPU  |
| 25. Printk indexing debugfs interface             | True       | Pour supporter l'interface de débogage de printk                                           |
| 26. Memory placement award NUMA scheduler         | True       | Pour supporter la planification NUMA aware                                                 |
| 27. Checkpoint/restore support                    | True       | Pour supporter la sauvegarde et la restauration des processus                              |
| 28. Automatic process group scheduling            | XXXX       | Planification automatique des groupes de processus                                         |
| 29. Kernel -> user space relay support            | XXXX       | Support de relais entre le noyau et l'espace utilisateur                                   |
| 30. Initial Ram filesystem and RAM disk ....      | initramfs  | Support de l'initramfs                                                                     |
| 31. Boot config support                           | True       | Pour supporter la configuration du démarrage                                               |
| 32. Preserve cpio archive mtimes in initramfs     | True       | Pour conserver les dates de modification des archives cpio dans l'initramfs                |
| 33. Compiler optimisation level                   | -O2        | Niveau d'optimisation du compilateur                                                       |
| 34. Profiling support                             | True       | Pour supporter le profilage du système                                                     |

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
RCU (Read-Copy Update) est un mécanisme de synchronisation dans le noyau Linux. 

Ces options permettent un contrôle fin de la comportement de RCU.

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
01. Enable utilization clamping for RT/FAIR tasks : <Boolean>
02. Number of supported utilization clamp buckets : <Boolean>
```


| Option                                            | Valeur |
| ---                                               | -----  |
| 01. Enable utilization clamping for RT/FAIR tasks | True   |
| 02. Number of supported utilization clamp buckets | 5      |


<br />

#### 08. Control Group Support
```
01. Favor dynamic modification latency reduction by default : <Boolean>
02. Memory controller : <Boolean>
03. IO controller : <Boolean>
04. Utilization clamping per group of tasks : <Boolean>
05. PIDs controller : <Boolean>
06. RDMA controller : <Boolean>
07. Freezer controller : <Boolean>
08. HugeTLB controller : <Boolean>
09. Cpuset controller : <Boolean>
10. Include legacy /proc/pid/cpuset file : <Boolean>
11. Device controller : <Boolean>
12. Simple CPU accounting controller : <Boolean>
13. Perf controller : <Boolean>
14. Support for eBPF programs attached to cgroups : <Boolean>
15. Misc resource controller : <Boolean>
16. Debug controller : <Boolean>
```

| Nom du paramètre                                            | Valeur | Commentaire                                                                             |
| -----                                                       | -----  | -----                                                                                   |
| 01. Favor dynamic modification latency reduction by default | True   | Réduire la latence                                                                      |
| 02. Memory controller                                       | True   | Meilleure gestion de la mémoire                                                         |
| 03. IO controller                                           | True   | Optimiser les opérations d'entrée/sortie                                                |
| 04. Utilization clamping per group of tasks                 | True   | Permet de définir des limites d'utilisation CPU pour des groupes de tâches spécifiques  |
| 05. PIDs controller                                         | True   | Limiter le nombre de processus et de threads qu'un groupe de contrôle peut créer        |
| 06. RDMA controller                                         | False  | Généralement non nécessaire pour un usage standard                                      |
| 07. Freezer controller                                      | True   | Permet de suspendre et de reprendre l'exécution de groupes de processus                 |
| 08. HugeTLB controller                                      | True   | Permettre l'utilisation de grandes pages mémoire                                        |
| 09. Cpuset controller                                       | True   | Permettre une meilleure affectation des tâches aux cœurs du processeur                  |
| 10. Include legacy /proc/pid/cpuset file                    | False  | Incomplet                                                                               |
| 11. Device controller                                       | True   | Permet de gérer l'accès aux périphériques pour différents groupes de contrôle           |
| 12. Simple CPU accounting controller                        | True   | Fournit des statistiques basiques sur l'utilisation du CPU par groupe de contrôle       |
| 13. Perf controller                                         | True   | Permet une meilleure gestion des événements de performance                              |
| 14. Support for eBPF programs attached to cgroups           | True   | Offre des capacités avancées de traçage et de manipulation du noyau                     |
| 15. Misc resource controller                                | No     | Incomplet                                                                               |
| 16. Debug controller                                        | False  | Eviter toute surcharge inutile en production                                            |

<br />

#### 09. Namespaces Support
```
01. UTS namespace     : <Boolean>
02. TIME namespace    : <Boolean>
03. IPC namespace     : <Boolean>
04. User namespace    : <Boolean>
05. PID Namespaces    : <Boolean>
06. Network namespace : <Boolean>
```

| Nom du paramètre      | Valeur | Commentaire |
| -----                 | -----  | -----       |
| 01. UTS namespace     | True   | Permet d'isoler les identifiants du système comme le nom d'hôte |
| 02. TIME namespace    | True   | Isole la vue du temps système |
| 03. IPC namespace     | True   | Isole les ressources de communication inter-processus |
| 04. User namespace    | True   | Permet de mapper les utilisateurs et groupes entre l'hôte et le conteneur |
| 05. PID Namespaces    | True   | Isole l'espace des identifiants de processus |
| 06. Network namespace | False  | Désactivé pour permettre au conteneur d'utiliser directement la pile réseau de l'hôte, ce qui est souvent préférable sur un PC de bureau |

<br />

#### 10. Configure standard kernel features
Ces paramètres sont optimisés pour un usage général sur un système moderne comme le Ryzen 7 3700X.

Ils activent les fonctionnalités importantes pour les performances et la stabilité, tout en désactivant les options obsolètes ou celles qui ne sont pas nécessaires pour un usage courant.

```
01. Enable 16-bit UID system calls : <boolean>
02. Multiple users, groups and capabilities support : <boolean>
03. sgetmask/ssetmask syscalls support : <boolean>
04. Sysfs syscall support : <boolean>
05. open by fhandle syscalls : <boolean>
06. Posix Clocks & timers : <boolean>
07. Enable support for printk : <boolean>
08. BUG() support : <boolean>
09. Enable ELF core dumps : <boolean>
10. Enable PC-Speaker support : <boolean>
11. Enable smaller-sized data structures for core (NEW) : <boolean>
12. Enable futex support : <boolean>
13. Enable eventpoll support : <boolean>
14. Enable signalfd() system call : <boolean>
15. Enable timerfd() system call : <boolean>
16. Enable eventfd() system call : <boolean>
17. Use full shmem filesystem : <boolean>
18. Enable AIO support : <boolean>
19. Enable IO uring support : <boolean>
20. Enable madvise/fadvise syscalls : <boolean>
21. Enable membarrier() system call : <boolean>
22. Enable kcmp() system call : <boolean>
23. Enable rseq() system call : <boolean>
24. Enable debugging of rseq() system call : <boolean>
25. Enable cachestat() system call (NEW) : <boolean>
26. PC/104 support : <boolean>
27. Load all symbols for debugging/ksymoops : <boolean>
28. Test the basic functions and performance of kallsyms (NEW) : <boolean>
29. Include all symbols in kallsyms : <boolean>
```

| Nom du paramètre                                               | Valeur | Commentaire |
| -----                                                          | -----  | -----       |
| 01. Enable 16-bit UID system calls                             | False  | Système de gestion d'utilisateurs obsolète, inutile sur les PC modernes |
| 02. Multiple users, groups and capabilities support            | True   | Permet d'avoir plusieurs comptes sur le même PC, essentiel pour la plupart des systèmes |
| 03. sgetmask/ssetmask syscalls support                         | False  | Anciennes commandes pour gérer les signaux, remplacées par de meilleures options |
| 04. Sysfs syscall support                                      | True   | Système de fichiers virtuel qui donne des infos sur le matériel, très utile pour la gestion du système |
| 05. open by fhandle syscalls                                   | True   | Permet d'ouvrir des fichiers de manière plus efficace dans certains cas |
| 06. Posix Clocks & timers                                      | True   | Gestion du temps standardisée, importante pour la compatibilité et la précision |
| 07. Enable support for printk                                  | True   | Permet au noyau d'afficher des messages, crucial pour le débogage et les logs système |
| 08. BUG() support                                              | False  | Aide à détecter et signaler les problèmes dans le noyau, important pour la stabilité |
| 09. Enable ELF core dumps                                      | True   | Crée des fichiers de diagnostic quand un programme plante, utile pour le débogage |
| 10. Enable PC-Speaker support                                  | False  | Support pour le petit haut-parleur interne, rarement utilisé de nos jours |
| 11. Enable smaller-sized data structures for core (NEW)        | False  | Peut économiser de la mémoire mais peut aussi réduire les performances |
| 12. Enable futex support                                       | True   | Mécanisme de synchronisation rapide, améliore les performances des applications multi-threads |
| 13. Enable eventpoll support                                   | True   | Améliore la gestion des événements d'entrée/sortie, bon pour les performances |
| 14. Enable signalfd() system call                              | True   | Améliorent la gestion des signaux, bons pour les performances |
| 15. Enable timerfd() system call                               | True   | Améliorent la gestion des timers, bons pour les performances |
| 16. Enable eventfd() system call                               | True   | Améliorent la gestion des événements, bons pour les performances |
| 17. Use full shmem filesystem                                  | True   | Système de fichiers en mémoire partagée complet, utile pour diverses applications |
| 18. Enable AIO support                                         | True   | Entrées/sorties asynchrones, peut améliorer les performances pour certaines applications |
| 19. Enable IO uring support                                    | True   | Nouvelle interface d'E/S asynchrone, peut grandement améliorer les performances |
| 20. Enable madvise/fadvise syscalls                            | True   | Permet d'optimiser l'utilisation de la mémoire et des fichiers |
| 21. Enable membarrier() system call                            | True   | Utile pour la synchronisation sur les systèmes multi-cœurs comme votre Ryzen |
| 22. Enable kcmp() system call                                  | True   | Permet de comparer des processus, utile pour certains outils système |
| 23. Enable rseq() system call                                  | True   | Permet des opérations atomiques plus rapides, bon pour les performances |
| 24. Enable debugging of rseq() system call                     | False  | Ajoute du code de débogage pour rseq, pas nécessaire sauf pour le développement |
| 25. Enable cachestat() system call (NEW)                       | True   | Fournit des statistiques sur l'utilisation du cache, utile pour l'optimisation |
| 26. PC/104 support                                             | False  | Support pour un type de matériel spécifique, inutile pour la plupart des PC de bureau |
| 27. Load all symbols for debugging/ksymoops                    | False  | Ajoutent des informations de débogage au noyau, utiles pour le développement |
| 28. Test the basic functions and performance of kallsyms (NEW) | False  | Ajoutent des informations de débogage au noyau, utiles pour le développement |
| 29. Include all symbols in kallsyms                            | False  | Ajoutent des informations de débogage au noyau, utiles pour le développement |

<br />

#### 11. Kernel Performance Events And Counters
```
01. Kernel performance events and counters Debug: use vmalloc to back perf mmap() buffers : <boolean>
```

| Nom du paramètre                                                                          | Valeur | Commentaire |
| -----                                                                                     | -----  | -----       |
| 01. Kernel performance events and counters Debug: use vmalloc to back perf mmap() buffers | False  | Le noyau utilise une méthode d'allocation mémoire différente, potentiellement plus rapide mais moins flexible |

<br />

#### 12. Kexec and crash features
```
1. Enable kexec system call : <boolean>
2. Enable kexec file based system call : <boolean>
3. Verify kernel signature during kexec_file_load() syscall : <boolean>
3A. Require a valid signature in kexec_file_load() syscall : <boolean>
3B. Enable Image signature verification support (ARM) : <boolean>
3C. Enable bzlmage signature verification support : <boolean>
4. kexec jump : <boolean>
5. kernel crash dumps : <boolean>
5A. Update the crash elfcorehdr on system configuration changes (NEW) : <boolean>
5B. Specify the maximum number of memory regions for the elfcorehdr (NEW) : <number>
```

| Nom du paramètre                                                          | Valeur | Commentaire |
| -----                                                                     | -----  | -----       |
| 1. Enable kexec system call                                               | True   |
| 2. Enable kexec file based system call                                    | True   |
| 3. Verify kernel signature during kexec_file_load() syscall               | True   |
| 3A. Require a valid signature in kexec_file_load() syscall                | True   |
| 3B. Enable Image signature verification support (ARM)                     | False  |
| 3C. Enable bzlmage signature verification support                         | False  |
| 4. kexec jump                                                             | True   |
| 5. kernel crash dumps                                                     | True   |
| 5A. Update the crash elfcorehdr on system configuration changes (NEW)     | True   |
| 5B. Specify the maximum number of memory regions for the elfcorehdr (NEW) | 16

<br />

#### 13. 64-Bit Kernel
```
64-bit kernel : <boolean>
```

| Nom du paramètre | Valeur | Commentaire                   |
| -----            | -----  | -----                         |
| 64-bit kernel    | True   | Système d'exploitation en x64 |







