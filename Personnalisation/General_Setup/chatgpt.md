--------------------------------------------------------------------------------------------------------
## I. Guide 
### A. Prompt
```
Quel est le meilleur paramètre pour un PC Ryzen 7 3700x sous Debian 12 :
```

#### 01. General Setup
```
- Compile also drivers which will not load : <Boolean>
- Compile the kernel with warnings as errors :  <Boolean>
- Compile test UAPI headers :  <Boolean>
- Local Version - apprend to kernel release: <String>
- Automatically apprend version information to the version string: <Boolean>
- Build ID Salt : <String>
- Kernel compression mode: <gzip, bzip, zstd, none>
- Default init path: <string>  
- Default Hostname: <string>
- System V IPC: <Boolean>
- POSIX Message queues : <Boolean>
- General notification queue : <Boolean>
- Enable process_vm_readv/writev_syscalls : <Boolean>
- uselib syscall (for libc5 and earlier)  : <Boolean>
- Auditing support : <Boolean>
- Preemption Model : <Boolean>
- Preemption behaviour defined on boot : <Boolean>
- Core Scheduling for SMT : <Boolean>
- CPU Isolation : <Boolean>
- Kernel .config support : <Boolean>
- Enable kernel headers throught /sys/kernel/kheaders.tar.xz : <Boolean>
- Kernel log buffer size : <Boolean>
- CPU Kernel log buffer size contribution : <Boolean>
- Printk indexing debugfs interface : <Boolean>
- Memory placement award NUMA scheduler : <Boolean>
- Checkpoint/restore support : <Boolean>
- Automatic process group scheduling : <number>
- Kernel -> user space relay support : <number>
- Initial Ram filesystem and RAM disk (initramfs/initrd) support : <string>
- Boot config support : <Boolean>
- Preserve cpio archive mtimes in intiramfs : <Boolean>
- Compiler optimisation level : <Boolean>
- Profiling support : <Boolean>
```



| Nom du paramètre                                  | Valeur     | Commentaire                                                                     |
| ------------------------------------------------- | ---------- | ------------------------------------------------------------------------------- |
| Compile also drivers which will not load          | false      | Sauf si vous avez des besoins spécifiques                                       |
| Compile the kernel with warnings as errors        | false      | Pour éviter les erreurs de compilation inutiles                                 | 
| Compile test UAPI headers                         | false      | Sauf si vous développez des applications qui utilisent ces headers              |
| Local Version - append to kernel release          | <Vide>     | Sauf si vous voulez personnaliser la version du noyau                           |
| Automatically apprend version information ...     | true       | Pour avoir des informations de version précises                                 |
| Build ID Salt                                     | <vide>     | Sauf si vous voulez personnaliser l'ID de build
| Kernel compression mode                           | zstd       | Pour une compression efficace
| Default init path                                 | /sbin/init | Chemin par défaut pour l'initialisation du système
| Default Hostname                                  | Debian     | Nom d'hôte par défaut, mais vous pouvez le personnaliser
| System V IPC                                      | true       | Pour supporter les IPC de System V
| POSIX Message queues                              | true       | Pour supporter les files d'attente de messages POSIX)
| General notification queue                        | true       | Pour supporter les notifications générales
| Enable process_vm_readv/writev_syscalls           | true       | Pour supporter les appels système de lecture et d'écriture de processus
| uselib syscall (for libc5 and earlier)            | false      | Sauf si vous utilisez une version de libc antérieure à la 5
| Auditing support                                  | true       | Pour supporter l'audit du système
| Preemption Model                                  | Desktop    | Pour un modèle de préemption adapté aux bureaux
| Preemption behaviour defined on boot              | true       | Pour définir le comportement de préemption au démarrage
| Core Scheduling for SMT                           | true       | Pour supporter la planification des cœurs pour SMT
| CPU Isolation                                     | false*     | Sauf si vous voulez isoler des CPU spécifiques
| Kernel .config support                            | true       | Pour supporter la configuration du noyau
| Enable kernel headers through .....               | true       | Pour supporter les headers du noyau
| Kernel log buffer size                            | 16         | taille par défaut du tampon de journalisation du noyau
| CPU Kernel log buffer size contribution           | 8          | Contribution par défaut de la taille du tampon de journalisation du noyau pour chaque CPU
| Printk indexing debugfs interface                 | true       | Pour supporter l'interface de débogage de printk
| Memory placement award NUMA scheduler             | true       | Pour supporter la planification NUMA aware
| Checkpoint/restore support                        | true       | Pour supporter la sauvegarde et la restauration des processus
| Automatic process group scheduling                | 2          | Planification automatique des groupes de processus
| Kernel -> user space relay support                | 2          | Pupport de relais entre le noyau et l'espace utilisateur
| Initial Ram filesystem and RAM disk ....          | initramfs  | Support de l'initramfs
| Boot config support                               | true       | Pour supporter la configuration du démarrage
| Preserve cpio archive mtimes in initramfs         | true       | Pour conserver les dates de modification des archives cpio dans l'initramfs
| Compiler optimisation level                       | -O2        | Niveau d'optimisation du compilateur
| Profiling support                                 | true       | Pour supporter le profilage du système

<br />

#### 02. IRQ Sub-System
```
1. Supportsparse irq numbering : <>
2. Expose irq internals in debugfs : <>
```

<br />

#### 03 Timers subsystem
```
1. Timer tick handling : <>
2. Force user context tracking : <>
3. Old Idle dynticks config : <>
4. High Resolution Timer Support : <>
5. ClockSource Watchdog maximum allowable skew (in ms) :  <>
```



| Nom du paramètre                                  | Valeur     | Commentaire                                                                     |
| ------------------------------------------------- | ---------- | ------------------------------------------------------------------------------- |
| Timer tick handling                               | -----      | XXXXXXXXXXXXXXXXXX|
| Force user context tracking                       | -----      | XXXXXXXXXXXXXXXXXX|
| Old Idle dynticks config                          | -----      | XXXXXXXXXXXXXXXXXX|
| High Resolution Timer Suppor                      | -----      | XXXXXXXXXXXXXXXXXX|
| ClockSource Watchdog maximum allowable skew       | -----      | XXXXXXXXXXXXXXXXXX|

<br />


#### 04 BPF subsystem
```
1. Enable bpf() system call : <>
2. Enable BPF Just In Time compiler : <>
3. Permanently enable BPF JIT and remove BPF interpreter : <>
4. Disable unprivileged BPF by default : <>
5. Enable BPF LSM Instrumentation : <>
```

| Nom du paramètre                                       | Valeur     | Commentaire                                                                     |
| ------------------------------------------------------ | ---------- | ------------------------------------------------------------------------------- |
| Enable bpf() system call                               | -----      | XXXXXXXXXXXXXXXXXX|
| Enable BPF Just In Time compiler                       | -----      | XXXXXXXXXXXXXXXXXX|
| Old Idle dynticks config                               | -----      | XXXXXXXXXXXXXXXXXX|
| Permanently enable BPF JIT and remove BPF interpreter  | -----      | XXXXXXXXXXXXXXXXXX|
| Disable unprivileged BPF by default                    | -----      | XXXXXXXXXXXXXXXXXX|
| Enable BPF LSM Instrumentation                         | -----      | XXXXXXXXXXXXXXXXXX|

<br />

#### 05 CPU task time and stats accounting
```
1. Cputime accounting : <>
2. Fine granularity task level IRQ time accounting : <>
3. BSD Process Accounting : <>
4. Export task/process statistics through netlink : <>
5. Pressure stall information tracking : <>
```

| Nom du paramètre                                 | Valeur     | Commentaire                                                                     |
| ------------------------------------------------ | ---------- | ------------------------------------------------------------------------------- |
| Cputime accounting                               | -----      | XXXXXXXXXXXXXXXXXX|
| Fine granularity task level IRQ time accounting  | -----      | XXXXXXXXXXXXXXXXXX|
| BSD Process Accounting                           | -----      | XXXXXXXXXXXXXXXXXX|
| Export task/process statistics through netlink   | -----      | XXXXXXXXXXXXXXXXXX|
| Pressure stall information tracking              | -----      | XXXXXXXXXXXXXXXXXX|


<br />

#### 06 RCU Subsystem
```
1. Make expert-level adjustments to RCU : <>
2. Configuration Force selection of TASKS_RCU : <>
3. Force selection of Tasks Rude RCU : <>
4. Force selection of Tasks Trace RCU : <>
4A. Tree-based hierarchical RCU fanout value : <>
4B. Tree-based hierarchical RCU leaf-level fanout value : <>
5. Enable RCU priority boosting : <>
6. Offload RCU callback processing from boot-selected CPUs : <>
7. Tasks Trace RCU readers use memory barriers in user and idle : <>
8. RCU callback lazy invocation functionality (NEW) : <>
9. RCU callback-batch backup time check : <>
```

| Nom du paramètre                                              | Valeur     | Commentaire                                                                     |
| ------------------------------------------------------------- | ---------- | ----- |
| Make expert-level adjustments to RCU                          | -----      | XXXXXXXXXXXXXXXXXX|
| Configuration Force selection of TASKS_RCU                    | -----      | XXXXXXXXXXXXXXXXXX|
| Force selection of Tasks Rude RCU                             | -----      | XXXXXXXXXXXXXXXXXX|
| ------------------------------------------------------------- | -----      | ----- |
| Force selection of Tasks Trace RCU                            | -----      | XXXXXXXXXXXXXXXXXX|
| Tree-based hierarchical RCU fanout value                      | -----      | XXXXXXXXXXXXXXXXXX|
| Tree-based hierarchical RCU leaf-level fanout value           | -----      | XXXXXXXXXXXXXXXXXX|
| ------------------------------------------------------------- | -----      | ----- |
| Enable RCU priority boosting                                  | -----      | XXXXXXXXXXXXXXXXXX|
| Offload RCU callback processing from boot-selected CPUs       | -----      | XXXXXXXXXXXXXXXXXX|
| Tasks Trace RCU readers use memory barriers in user and idle  | -----      | XXXXXXXXXXXXXXXXXX|
| RCU callback lazy invocation functionality (NEW)              | -----      | XXXXXXXXXXXXXXXXXX|
| RCU callback-batch backup time check                          | -----      | XXXXXXXXXXXXXXXXXX|



<br />

#### 07 Scheduler features
```
```

<br />

#### 08 Control Group Support
```
```

<br />

#### 09 Namespaces Support
```
```

<br />

#### 10 Configure standard kernel features
```
```

<br />

#### 11 Kernel Performance Events And Counters
```
```

<br />

#### 12 Kexec and crash features









