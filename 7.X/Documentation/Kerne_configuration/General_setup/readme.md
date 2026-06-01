| Option                                             | Valeur | Description                                                                 |
|----------------------------------------------------|--------|------------------------------------------------------------------------------|
[ ] Compile also drivers which will not load         |        | Compiler également des pilotes qui ne démarreront pas                        |
[ ] Compile the kernel with warnings as errors       |        | Compiler le noyau avec les avertissements considérés comme des erreurs        |
() Local version - append to kernel release          |        | Ajouter une version locale à la version du noyau                             |
[ ] Automatically append version information to the version string |  | Ajouter automatiquement des informations de version au nom du noyau           |
() Build ID Salt                                    |        | Selon le système, ajoute un sel unique pour chaque compilation               |
Kernel compression mode (ZSTD) ---&gt;                | ZSTD  | Mode de compression du noyau ( BZip2, LZMA, XZ, LZ0, LZ4, ZSTD |
() Default init path                                 |        | Chemin par défaut pour l'initialisation                                      |
((none)) Default hostname                            | none   | Nom d'hôte par défaut                                                        |
[*] System V IPC                                     | enabled| Activer le support IPC (Inter-Process Communication) du système V             |
[*] POSIX Message Queues                             | enabled| Activer les files de messages POSIX                                          |
[ ] General notification queue                       | disabled| Activer la file de notifications générales                                   |
[*] Enable process_vm_readv/writev syscalls          | enabled| Activer les systèmes d'appel process_vm_readv et process_vm_writev             |
-*- Auditing support                                 |        | Activer le suivi des modifications du système (non renseigné)                 |
IRQ subsystem ---&gt;                                  |        | Système IRQ (Interrupt Request)                                              |
Timers subsystem ---&gt;                               |        | Système de compteurs                                                        |
BPF subsystem ---&gt;                                   |        | Sous-système BPF (Berkeley Packet Filter)                                    |
Preemption Model (Scheduler controlled preemption model) ---&gt; | default| Modèle de prééminence du planificateur                                        |
[ ] Fully Preemptible Kernel (Real-Time)             | disabled| Noyau complètement préemptible pour des applications temps-réel              |
[*] Preemption behaviour defined on boot             | enabled| Comportement de préémination défini lors du démarrage                       |
[ ] Core Scheduling for SMT                           | disabled| Planification de noyaux pour le Muti-Threading (SMT)                          |
[ ] Extensible Scheduling Class                      | disabled| Classe de planification élargie                                             |
CPU/Task time and stats accounting ---&gt;           |        | Compte le temps et les statistiques du CPU et des tâches                      |
-*- CPU isolation                                     |        | Isolation du CPU                                                              |
RCU Subsystem ---&gt;                                  |        | Système RCU (Read-Copy-Update)                                               |
< > Kernel .config support                            | disabled| Support de la configuration du noyau (.config)                               |
< > Enable kernel headers through /sys/kernel/kheaders.tar.xz | disabled| Activer les en-têtes du noyau via /sys/kernel/kheaders.tar.xz                 |
(17) Kernel log buffer size (16 => 64KB, 17 => 128KB)   | 17     | Taille de la file d'attente des journaux du noyau (17 = 128KB)               |
(12) CPU kernel log buffer size contribution (13 => 8 KB, 17 => 128KB) | 17    | Contribution de la taille de la file d'attente des journaux du noyau au CPU (17 = 128KB) |
[ ] Printk indexing debugfs interface                | disabled| Interface
