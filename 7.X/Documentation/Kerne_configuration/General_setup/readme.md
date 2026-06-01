| Option | Valeur | Description |
|:------|:-----|:------------|
| Compile also drivers which will not load                       |   [ ] | Compilez également les pilotes qui ne démarreraient pas. |
| Compile the kernel with warnings as errors                     |   [ ] | Compiler le noyau avec les avertissements considérés comme des erreurs. |
| Local version - append to kernel release                       |   ( ) | Ajoute une version locale au numéro de libération du noyau. |
| Automatically append version information to the version string |   [ ] | Ajoute automatiquement l'information de version à la chaîne de version. |
| Build ID Salt |   ( ) | Sel de build_id.                       |
| [Kernel compression mode (ZSTD)](https://github.com/MarcJaffre/Kernel/blob/main/7.X/Documentation/Kerne_configuration/General_setup/Kernel_compression_mode_(ZSTD).md) |   ---&gt; | Mode de compression du noyau (ZSTD). |
| Default init path |   [*] | Chemin par défaut pour l'initialisation. |
| Default hostname |   ((none)) | Nom d'hôte par défaut. |
| System V IPC |   [*] | Support du système d'échange de messages IPC (System V). |
| POSIX Message Queues |   [*] | Files de messages POSIX. |
| General notification queue |   [ ] | File de notifications générales. |
| Enable process_vm_readv/writev syscalls |   [*] | Activer les appels systèmes `process_vm_readv` et `writev`. |
| Auditing support |   -*- | Support d'audit. |
| [IRQ subsystem](https://github.com/MarcJaffre/Kernel/blob/main/7.X/Documentation/Kerne_configuration/General_setup/IRQ_subsystem.md)     |   ---&gt; | Sous-système des interruptions (IRQ). |
| [Timers subsystem](ici)  |   ---&gt; | Sous-système des compteurs de temps. |
| [BPF subsystem](ici)     |   ---&gt; | Sous-système BPF (Berkeley Packet Filter). |
| [Preemption Model](ici)  |   ---&gt; | Modèle de préemptibilité (sous-contrôlé par le scheduleur). |
| Fully Preemptible Kernel (Real-Time) |   [ ] | Noyau entièrement préemptible (réalisation temps réel). |
| Preemption behaviour defined on boot |   [*] | Comportement de préemption défini au démarrage. |
| Core Scheduling for SMT |   [ ] | Planification des noyaux pour SMT (Multiprocessing Simultaneous Multithreading). |
| Extensible Scheduling Class |   [ ] | Classe de planification étendue. |
| [CPU/Task time and stats accounting](ici)  |   ---&gt; | Comptage du temps CPU et statistiques des tâches. |
| CPU isolation |   -*- | Isolation du processeur. |
| [RCU Subsystem](ici) |   ---&gt; | Sous-système RCU (Read-Copy-Update). |
| Kernel .config support |   < > | Support de `.config` du noyau. |
| Enable kernel headers through /sys/kernel/kheaders.tar.xz |   < > | Activer les en-têtes du noyau via `/sys/kernel/kheaders.tar.xz`. |
| Kernel log buffer size |   (17) | Taille du tampon des journaux de noyau (16 => 64KB, 17 => 128KB). |
| CPU kernel log buffer size contribution |   (12) | Contribution de la taille du tampon des journaux CPU au noyau (13 => 8 KB, 17 => 128KB). |
| Printk indexing debugfs interface |   [ ] | Interface de `debugfs` pour l'indexation `printk`. |
| [Scheduler features](ici) |   ---&gt; | Fonctionnalités du planificateur. |
| Memory placement aware NUMA scheduler |   [*] | Planificateur NUMA conscient de la mise en place des mémoires. |
| Automatically enable NUMA aware memory/task placement |   [*] | Activer automatiquement le placement mémoire/du processus NUMA conscient. |
| Control Group support |   -*- | Support des groupes de contrôle. |
| Namespaces support |   [*] | Support des espaces de noms. |
| Checkpoint/restore support |   [*] | Support de checkpoint et restauration. |
