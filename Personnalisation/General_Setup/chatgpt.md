--------------------------------------------------------------------------------------------------------
## I. Guide 
### A. Prompt
```
Quel est le meilleur paramètre pour un PC Ryzen 7 3700x sous Debian 12 :
```

#### 01. General Setup
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
```
1. Supportsparse irq numbering : <Boolean>
2. Expose irq internals in debugfs : <Boolean>
```

| Nom du paramètre                    | Valeur     | Commentaire        |
| -----                               | -----      | -----              |
| 1. Supportsparse irq numbering      | XXXXX      | XXXXXXXXXXXXXXXXXX |
| 2. Expose irq internals in debugfs  | XXXXX      | XXXXXXXXXXXXXXXXXX |

<br />

#### 03. Timers subsystem
```
1. Timer tick handling : <Boolean>
2. Force user context tracking : <Boolean>
3. Old Idle dynticks config : <Boolean>
4. High Resolution Timer Support : <Boolean>
5. ClockSource Watchdog maximum allowable skew (in ms) : <Number>
```

| Nom du paramètre                                  | Valeur     | Commentaire        |
| -----                                             | -----      | -----              |
| 1. Timer tick handling                            | -----      | XXXXXXXXXXXXXXXXXX |
| 2. Force user context tracking                    | -----      | XXXXXXXXXXXXXXXXXX |
| 3. Old Idle dynticks config                       | -----      | XXXXXXXXXXXXXXXXXX |
| 4. High Resolution Timer Suppor                   | -----      | XXXXXXXXXXXXXXXXXX |
| 5. ClockSource Watchdog maximum allowable skew    | -----      | XXXXXXXXXXXXXXXXXX |

<br />

#### 04. BPF subsystem
```
1. Enable bpf() system call : <Boolean>
2. Enable BPF Just In Time compiler : <Boolean>
3. Permanently enable BPF JIT and remove BPF interpreter : <Boolean>
4. Disable unprivileged BPF by default : <Boolean>
5. Enable BPF LSM Instrumentation : <Boolean>
```

| Nom du paramètre                                          | Valeur     | Commentaire        |
| -----                                                     | -----      | -----              |
| 1. Enable bpf() system call                               | -----      | XXXXXXXXXXXXXXXXXX |
| 2. Enable BPF Just In Time compiler                       | -----      | XXXXXXXXXXXXXXXXXX |
| 3. Old Idle dynticks config                               | -----      | XXXXXXXXXXXXXXXXXX |
| 4. Permanently enable BPF JIT and remove BPF interpreter  | -----      | XXXXXXXXXXXXXXXXXX |
| 5. Disable unprivileged BPF by default                    | -----      | XXXXXXXXXXXXXXXXXX |
| 6. Enable BPF LSM Instrumentation                         | -----      | XXXXXXXXXXXXXXXXXX |

<br />

#### 05. CPU task time and stats accounting
```
1. Cputime accounting : <Boolean>
2. Fine granularity task level IRQ time accounting : <Boolean>
3. BSD Process Accounting : <Boolean>
4. Export task/process statistics through netlink : <Boolean>
5. Pressure stall information tracking : <Boolean>
```

| Nom du paramètre                                    | Valeur     | Commentaire        |
| -----                                               | -----      | -----              |
| 1. Cputime accounting                               | -----      | XXXXXXXXXXXXXXXXXX |
| 2. Fine granularity task level IRQ time accounting  | -----      | XXXXXXXXXXXXXXXXXX |
| 3. BSD Process Accounting                           | -----      | XXXXXXXXXXXXXXXXXX |
| 4. Export task/process statistics through netlink   | -----      | XXXXXXXXXXXXXXXXXX |
| 5. Pressure stall information tracking              | -----      | XXXXXXXXXXXXXXXXXX |

<br />

#### 06. RCU Subsystem
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

| Nom du paramètre                                                 | Valeur     | Commentaire        |
| -----                                                            | -----      | -----              |
| 1. Make expert-level adjustments to RCU                          | -----      | XXXXXXXXXXXXXXXXXX |
| 2. Configuration Force selection of TASKS_RCU                    | -----      | XXXXXXXXXXXXXXXXXX |
| 3. Force selection of Tasks Rude RCU                             | -----      | XXXXXXXXXXXXXXXXXX |
| -----                                                            | -----      | -----              |
| 4. Force selection of Tasks Trace RCU                            | -----      | XXXXXXXXXXXXXXXXXX |
| 4A. Tree-based hierarchical RCU fanout value                     | -----      | XXXXXXXXXXXXXXXXXX |
| 4B. Tree-based hierarchical RCU leaf-level fanout value          | -----      | XXXXXXXXXXXXXXXXXX |
| -----                                                            | -----      | -----              |
| 5. Enable RCU priority boosting                                  | -----      | XXXXXXXXXXXXXXXXXX |
| 6. Offload RCU callback processing from boot-selected CPUs       | -----      | XXXXXXXXXXXXXXXXXX |
| 7. Tasks Trace RCU readers use memory barriers in user and idle  | -----      | XXXXXXXXXXXXXXXXXX |
| 8. RCU callback lazy invocation functionality (NEW)              | -----      | XXXXXXXXXXXXXXXXXX |
| 9. RCU callback-batch backup time check                          | -----      | XXXXXXXXXXXXXXXXXX |


<br />

#### 07. Scheduler features
```
```

<br />

#### 08. Control Group Support
```
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
