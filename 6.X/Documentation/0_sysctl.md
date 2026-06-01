--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

sysctl -a


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
| Paramètre                            | Valeur                         | Description Simple                                                                                           |
|--------------------------------------|--------------------------------|--------------------------------------------------------------------------------------------------------------|
| `abi.vsyscall32`                     | 1                              | Active ou désactive l'utilisation du syscall32 pour l'ABI.                                                   |
| `crypto.fips_enabled`                | 0                              | Indique si le mode FIPS est activé (0 = désactivé, 1 = activé).                                              |
| `crypto.fips_name`                   | Linux Kernel Cryptographic API | Nom du backend cryptographique utilisé par le noyau.                                                         |
| `crypto.fips_version`                | 6.12.74+deb13+1-amd64          | Version spécifique du mode FIPS.                                                                             |
| `debug.exception-trace`              | 1                              | Active ou désactive la trace des exceptions pour aider à la débogage.                                        |
| `debug.kprobes-optimization`         | 1                              | Activer l'optimisation des kprobes, qui peuvent être utilisés pour la instrumentation.                       |
| `dev.hpet.max-user-freq`             | 64                             | Définit la fréquence maximale du HPET (High Precision Event Timer) utilisé par les applications utilisateur. |
| `dev.i915.oa_max_sample_rate`        | 100000                         | Définit le taux maximum d'échantillonnage pour l'optimisation d'affichage (OA).                              |
| `dev.i915.perf_stream_paranoid`      | 1                              | Paramètre de sécurité pour la gestion des flux de performances.                                              |
| `dev.mac_hid.mouse_button2_keycode`  | 97                             | Code clé pour le bouton 2 du mouse button emulation.                                                         |
| `dev.mac_hid.mouse_button3_keycode`  | 100                            | Code clé pour le bouton 3 du mouse button emulation.                                                         |
| `dev.mac_hid.mouse_button_emulation` | 0                              | Activer ou désactiver l'emulation des boutons de la souris.                                                  |
| `dev.parport.default.spintime`       | 500                            | Temps de rotation par défaut pour le port parallèle, en microsecondes.                                       |
| `dev.parport.default.timeslice`      | 200                            | Temps d'allocation du temps par défaut pour le port parallèle, en microsecondes.                             |
| `dev.scsi.logging_level`             | 0                              | Niveau de logging du module SCSI (0 = minimale).                                                             |
| `dev.tty.ldisc_autoload`             | 1                              | Activer l'autoloading des line disciplines pour les terminaux.                                               |
| `dev.tty.legacy_tiocsti`             | 0                              | Désactiver le comportement ancien de la fonction tiocsti.                                                    |


| Paramètre                            | Valeur                         | Description Simple                                                                                           |
|--------------------------------------|--------------------------------|--------------------------------------------------------------------------------------------------------------|
| `fs.aio-max-nr`                      | 65536                          | Nombre maximum de requêtes asynchrones simultanées.                                                          |
| `fs.aio-nr`                          | 0                              | Nombre actuel de requêtes asynchrones en cours.                                     |
| `fs.binfmt_misc.python3/13`          | enabled                        | Active le support pour l'interpréteur Python 3.13 dans binfmt_misc.                 |
| `fs.binfmt_misc.status`              | enabled                        | Indique si binfmt_misc est activé.                                                 |
| `fs.dentry-state`                    | 47661 35149 45 0 12529 0       | Statut des dentries (direntries).                                                   |
| `fs.dir-notify-enable`               | 1                              | Active la notification des changements de répertoire.                              |
| `fs.epoll.max_user_watches`          | 836585                         | Nombre maximum d'événements epoll par utilisateur.                                  |
| `fs.fanotify.max_queued_events`      | 16384                          | Taille maximale de la file d'attente pour les notifications fanotify.               |
| `fs.fanotify.max_user_groups`        | 128                            | Nombre maximum de groupes utilisateurs pour les notifications fanotify.            |
| `fs.fanotify.max_user_marks`         | 30834                          | Taille maximale des marques utilisateur pour les notifications fanotify.            |
| `fs.file-max`                        | 9223372036854775807            | Nombre maximum de fichiers ouverts par le système.                                  |
| `fs.file-nr`                         | 7776 0 9223372036854775807     | Statut des fichiers en cours d'utilisation (utilisés, libérables, maximum).         |
| `fs.inode-nr`                        | 35278 532                      | Statut des inodes (nombre total, utilisés, libérables).                             |
| `fs.inotify.max_queued_events`       | 16384                          | Taille maximale de la file d'attente pour les notifications inotify.                |
| `fs.inotify.max_user_instances`      | 128                            | Nombre maximum d'instances inotify par utilisateur.                                 |
| `fs.inotify.max_user_watches`        | 28977                          | Taille maximale des fichiers de surveillance pour les notifications inotify.       |
| `fs.lease-break-time`                | 45                             | Durée (en secondes) avant le break des contrats de fichier.                         |
| `fs.leases-enable`                   | 1                              | Active la gestion des contrats de fichiers.                                        |
| `fs.mount-max`                       | 100000                         | Nombre maximum d'entrées dans `/etc/fstab`.                                        |
| `fs.mqueue.msg_default`              | 10                             | Valeur par défaut pour les messages de la file de messagerie mqueue.                |
| `fs.mqueue.msg_max`                  | 10                             | Taille maximale des messages de la file de messagerie mqueue.                       |
| `fs.mqueue.msgsize_default`          | 8192                           | Taille par défaut pour les messages de la file de messagerie mqueue.               |
| `fs.mqueue.msgsize_max`              | 8192                           | Taille maximale des messages de la file de messagerie mqueue.                       |
| `fs.mqueue.queues_max`               | 256                            | Nombre maximum de files de messagerie mqueue.                                      |
| `fs.nr_open`                         | 1073741816                     | Nombre total de fichiers ouverts dans le système.                                  |
| `fs.overflowgid`                     | 65534                          | GID (Group ID) par défaut pour les fichiers qui dépassent l'espace d'identificateurs.|
| `fs.overflowuid`                     | 65534                          | UID (User ID) par défaut pour les fichiers qui dépassent l'espace d'identificateurs. |
| `fs.pipe-max-size`                   | 1048576                        | Taille maximale d'un tube de communication en octets.                              |
| `fs.pipe-user-pages-hard`            | 0                              | Taille maximale du buffer de page pour les tubes (limite dure).                     |
| `fs.pipe-user-pages-soft`            | 16384                          | Taille maximale du buffer de page pour les tubes (limite souple).                  |
| `fs.protected_fifos`                 | 1                              | Active la protection des tubes de communication.                                   |
| `fs.protected_hardlinks`             | 1                              | Active la protection des liens dur.                                                |
| `fs.protected_regular`               | 2                              | Active la protection des fichiers réguliers.                                       |
| `fs.protected_symlinks`              | 1                              | Active la protection des liens symboliques.                                        |
| `fs.quota.allocated_dquots`          | 0                              | Nombre de quotas alloués.                                                           |
| `fs.quota.cache_hits`                | 0                              | Nombres de hits sur le cache de quota.                                             |
| `fs.quota.drops`                     | 0                              | Nombres de drop (échecs) sur le cache de quota.                                     |
| `fs.quota.free_dquots`               | 0                              | Nombre de quotas libres.                                                           |
| `fs.quota.lookups`                   | 0                              | Nombres de lookups de quota effectués.                                             |
| `fs.quota.reads`                     | 0                              | Nombres de lectures sur le cache de quota.                                         |
| `fs.quota.syncs`                     | 0                              | Nombres de syncs (écrasements) sur le cache de quota.                               |
| `fs.quota.writes`                    | 0                              | Nombres d'écritures sur le cache de quota.                                          |
| `fs.suid_dumpable`                   | 0                              | Désactive l'écrasement du mode SUID lors du débogage.                               |
| `fs.verity.require_signatures`       | 0                              | Active ou désactive la vérification des signatures pour le vérifiabilité (fsverity).|

| Paramètre                            | Valeur                         | Description Simple                                                                                           |
|--------------------------------------|--------------------------------|--------------------------------------------------------------------------------------------------------------|
| kernel.acct                   | 4 2 30 | Comptage des tâches système |
| kernel.acpi_video_flags       | 0      | Modes d'affichage vidéo ACPI désactivés |
| kernel.apparmor_display_secid_mode | 0     | Affichage des IDs de sécurité APPARMOR désactivé |
| kernel.apparmor_restrict_unprivileged_unconfined | 0    | Restriction d'applications non confinées par APPARMOR désactivée |
| kernel.arch                   | x86_64 | Architecture du système (x86_64) |
| kernel.auto_msgmni            | 0      | Contrôle automatique de la taille du message mnémotechnique désactivé |
| kernel.bootloader_type        | 33     | Type de chargeur de démarrage (0x21, BIOS) |
| kernel.bootloader_version     | 1      | Version du chargeur de démarrage |
| kernel.bpf_stats_enabled      | 0      | Statistiques BPF désactivées |
| kernel.cad_pid                | 1      | PID du processus pour le signalement CAD activé (PID=1) |
| kernel.cap_last_cap           | 40     | Dernier cap d'autorisation Unix (cap-NG) (CAP_LAST_CAP) |
| kernel.core_file_note_size_limit | 4194304 | Taille maximale des notes dans les fichiers noyau en octets (4 Mo) |
| kernel.core_pattern           | core   | Nom du fichier de dump de coredump par défaut |
| kernel.core_pipe_limit        | 0      | Limite de pipe pour le coredump désactivée |
| kernel.core_sort_vma          | 0      | Tri des zones mémoire dans les fichiers noyau désactivé |
| kernel.core_uses_pid          | 1      | Utilisation du PID dans l'nom du fichier de dump activé |
| kernel.ctrl-alt-del           | 0      | Traitement du raccourci Ctrl+Alt+Del désactivé |
| kernel.dmesg_restrict         | 1      | Restricion des messages d'erreurs dans le buffer d'erreurs désactivée (1) |
| kernel.domainname             | (none) | Nom de domaine non configuré |
| kernel.firmware_config.force_sysfs_fallback | 0    | Forcer la récupération des informations du firmware par le SFS désactivé |
| kernel.firmware_config.ignore_sysfs_fallback | 0   | Ignorer la récupération des informations du firmware par le SFS désactivé |
| kernel.ftrace_dump_on_oops    | 0      | Enregistrement d'un dump lors d'une erreur fatale désactivé |
| kernel.ftrace_enabled         | 1      | Suivi en temps réel activé |
| kernel.hardlockup_all_cpu_backtrace | 0   | Backtraces sur tous les cœurs pour une panne d'exécution désactivée |
| kernel.hardlockup_panic        | 0      | Panique lors d'une perte de synchronisation désactivée |
| kernel.hostname               | vm65n  | Nom du hôte (vm65n) |
| kernel.hung_task_all_cpu_backtrace | 0   | Backtraces sur tous les cœurs pour des tâches en attente désactivé |
| kernel.hung_task_check_count  | 4194304| Compteur de vérification des tâches en attente (4 Mo) |
| kernel.hung_task_check_interval_secs | 0   | Intervalle de vérification des tâches en attente désactivé |
| kernel.hung_task_panic        | 0      | Panique lors d'un blocage de tâche désactivée |
| kernel.hung_task_timeout_secs | 120    | Durée maximale avant un signal d'alerte (2 minutes) |
| kernel.hung_task_warnings     | 10     | Nombre maximal d'avertissements pour une tâche en attente (10) |
| kernel.io_delay_type          | 0      | Type de retard I/O désactivé |
| kernel.io_uring_disabled     | 0      | IO-uring désactivée |
| kernel.io_uring_group        | -1     | Groupe d'IO-uring désactivé (groupe non défini) |
| kernel.kexec_load_disabled    | 0      | Désactivation du chargement par kexec désactivée |
| kernel.kexec_load_limit_panic | -1     | Limite de kexec en cas d'erreur non configurée (pas de limitation) |
| kernel.kexec_load_limit_reboot | -1   | Limite de kexec après redémarrage non configurée (pas de limitation) |
| kernel.keys.gc_delay          | 300    | Délai avant la collecte de mémoire pour les clés, en secondes (5 minutes) |
| kernel.keys.maxbytes          | 20000  | Taille maximale des fichiers de clés en octets (20 Ko) |
| kernel.keys.maxkeys           | 200    | Nombre maximum de clés dans le système (200) |
| kernel.keys.persistent_keyring_expiry | 259200 | Durée d'expiration des keyrings persistants, en secondes (3 jours) |
| kernel.keys.root_maxbytes     | 25000000 | Taille maximale des fichiers de clés pour le noyau racine en octets (25 Mo) |
| kernel.keys.root_maxkeys      | 1000000 | Nombre maximum de clés dans le keyring du noyau racine (1 million) |
| kernel.kptr_restrict          | 0      | Restricion des adresses virtuelles dans les messages d'erreurs désactivée |
| kernel.max_lock_depth         | 1024   | Profondeur maximale des verrous (1024) |
| kernel.max_rcu_stall_to_panic | 0      | Durée maximale avant une panique en cas de stall RCU désactivée |
| kernel.modprobe               | /sbin/modprobe | Chemin vers la commande modprobe par défaut (/sbin/modprobe) |
| kernel.modules_disabled       | 0      | Désactivation des modules noyau désactivée |
| kernel.msgmax                 | 8192   | Taille maximale d'un message de communication interprocessus en octets (8 Ko) |
| kernel.msgmnb                 | 16384  | Taille totale du buffer pour les messages de communication interprocessus, en messages (16 Ko) |
| kernel.msgmni                 | 32000  | Nombre maximum de noyaux de message de communication interprocessus (32000) |
| kernel.msg_next_id            | -1     | ID suivant pour les messages non configuré (pas d'ID assigné) |
| kernel.ngroups_max            | 65536  | Nombre maximum de groupes par utilisateur (65536) |
| kernel.nmi_watchdog           | 1      | Détecteur NMI en mode watchdog activé |
| kernel.ns_last_pid            | 2748   | PID du dernier namespace (2748) |
| kernel.numa_balancing         | 0      | Équilibrage NUMA désactivé |
| kernel.numa_balancing_promote_rate_limit_MBps | 65536 | Limite de promotion pour l'équilibrage NUMA, en Mo/s (64 Ko/s) |
| kernel.oops_all_cpu_backtrace | 0      | Backtraces sur tous les cœurs pour une panne d'exécution désactivé |
| kernel.oops_limit             | 10000  | Nombre maximum de messages d'erreurs avant une action corrective (10000) |
| kernel.osrelease              | 6.12.74+deb13+1-amd64 | Version du noyau (6.12.74+deb13+1-amd64) |
| kernel.ostype                 | Linux  | Type d'OS (Linux) |
| kernel.overflowgid             | 65534  | GID par défaut pour les utilisateurs overflow (65534) |
| kernel.overflowuid             | 65534  | UID par défaut pour les utilisateurs overflow (65534) |
| kernel.panic                  | 0      | Panique automatique après une erreur désactivée |
| kernel.panic_on_io_nmi        | 0      | Panique en cas de NMI pour une opération d'écriture désactivée |
| kernel.panic_on_oops          | 0      | Panique lors d'une erreur fatale désactivée |
| kernel.panic_on_rcu_stall     | 0      | Panique en cas de bloqueur RCU désactivé |
| kernel.panic_on_unrecovered_nmi | 0   | Panique après une NMI non récupérée désactivée |
| kernel.panic_on_warn          | 0      | Panique en cas d'avertissement désactivée |
| kernel.panic_print            | 0      | Imprimer un message de panique désactivé |
| kernel.perf_cpu_time_max_percent | 25   | Pourcentage maximal du temps CPU pour les événements perf (25%) |
| kernel.perf_event_max_contexts_per_stack | 8    | Contextes par stack maximum pour les événements perf (8) |
| kernel.perf_event_max_sample_rate | 100000 | Taux de prise d'échantillon maximum pour les événements perf (100 000/s) |
| kernel.perf_event_max_stack   | 127    | Taille maximale du stack pour les événements perf (127) |
| kernel.perf_event_mlock_kb    | 516    | Taille en Ko pour la mémoire allouée par mlock pour les événements perf (516 Ko) |
| kernel.perf_event_paranoid    | 3      | Niveau de sécurité pour les événements perf (3) |
| kernel.pid_max                | 4194304 | PID maximum du système (4 194 304) |
| kernel.poweroff_cmd           | /sbin/poweroff | Commande utilisée pour arrêter le système (/sbin/poweroff) |
| kernel.print-fatal-signals   | 0      | Imprimer des signaux fataux désactivé |
| kernel.printk                 | 4 4 1 7 | Paramètres de niveau d'impression du noyau (4: erreurs, 4: avertissements, 1: informations, 7: détails) |
| kernel.printk_delay           | 0      | Délai d'impression des messages d'erreur désactivé |
| kernel.printk_devkmsg         | on     | Imprimer les messages dans devkmsg activé |
| kernel.printk_ratelimit       | 5      | Limite de fréquence d'impression par message (5 messages/s) |
| kernel.printk_ratelimit_burst | 10     | Durée maximale de la burst pour la limitation (10 secondes) |
| kernel.pty.max                | 4096   | Nombre maximum d'pty disponibles (4096) |
| kernel.pty.nr                 | 2      | Nombre actuel d'pty attribués (2) |
| kernel.pty.reserve            | 1024   | Nombre de pty réservés pour le noyau (1024) |
| kernel.random.boot_id         | 8e0fe330-d6fc-4752-92a4-6669958d7b27 | Identifiant de démarrage aléatoire (UUID) |
| kernel.random.entropy_avail   | 256    | Niveau d'entropy disponible (256 bits) |
| kernel.randomize_va_space     | 2      | Espace virtuel randomisé activé (2) |
| kernel.random.poolsize        | 256    | Taille de la pool d'entropy (256 bits) |
| kernel.random.urandom_min_reseed_secs | 60   | Temps minimal entre les resèvements de l'urandom en secondes (60s) |
| kernel.random.uuid            | c809c900-047f-4a4f-b7dd-3f6f1b8ea716 | UUID aléatoire généré au démarrage du système |
| kernel.random.write_wakeup_threshold | 256   | Seuil de réveil en écriture (256) |
| kernel.real-root-dev          | 0      | Indice de périphérique root réel désactivé |
| kernel.sched_autogroup_enabled | 1      | Gestion automatique des groupes d'ordonnancement activée |
| kernel.sched_cfs_bandwidth_slice_us | 5000  | Taille du slice CFS (microsecondes) (5000 us) |
| kernel.sched_deadline_period_max_us | 4194304 | Période maximale de ligne d'attente (4 194 304 microsecondes) |
| kernel.sched_deadline_period_min_us | 100    | Période minimale de ligne d'attente (100 microsecondes) |
| kernel.sched_rr_timeslice_ms  | 100    | Slice de rotation du temps réel en millisecondes (100 ms) |
| kernel.sched_rt_period_us     | 1000000 | Période de RT en microsecondes (1 000 000 us) |
| kernel.sched_rt_runtime_us    | 950000 | Durée maximale d'exécution RT en microsecondes (950 000 us) |
| kernel.sched_schedstats       | 0      | Statistiques d'ordonnancement désactivées |
| kernel.seccomp.actions_avail  | kill_process kill_thread trap errno user_notif trace log allow | Actions disponibles pour seccomp |
| kernel.seccomp.actions_logged | kill_process kill_thread trap errno user_notif trace log | Actions enregistrées par seccomp |
| kernel.sem                     | 32000 1024000000 500 32000  | Nombre, taille maximale d'octets, nombre de slots et age de semaphore |
| kernel.sem_next_id             | -1     | ID suivant pour les semaphores non configuré (pas d'ID assigné) |
| kernel.shmall                  | 18446744073692774399 | Taille maximale des pools de segments partagés, en pages |
| kernel.shmmax                  | 18446744073692774399 | Taille maximale d'un segment partagé, en octets |
| kernel.shmmni                  | 4096   | Nombre maximum de noyaux de segments partagés (4096) |
| kernel.shm_next_id             | -1     | ID suivant pour les segments partagés non configuré (pas d'ID assigné) |
| kernel.shm_rmid_forced         | 0      | Forcer la destruction des segments partagés désactivée |
| kernel.softlockup_all_cpu_backtrace | 0   | Suivi de backtrace lors de tous les soft lockups désactivé |
| kernel.softlockup_panic        | 0      | Panique lors de soft lockups désactivée |
| kernel.soft_watchdog          | 1      | Détecteur de soft lockups activé |
| kernel.split_lock_mitigate    | 1      | Mitigation des splits locks activée |
| kernel.stack_tracer_enabled   | 0      | Suivi du stack désactivé |
| kernel.sysctl_writes_strict   | 1      | Écritures strictes de sysctl activées |
| kernel.sysrq                   | 438    | Système de ruban de raccourci activé (0x1b6) |
| kernel.tainted                | 0      | Marqueur d'erreurs système désactivé |
| kernel.task_delayacct         | 0      | Comptage des retards des tâches désactivé |
| kernel.threads-max            | 28418  | Nombre maximum de threads (28418) |
| kernel.timer_migration        | 1      | Migration de l'horloge activée |
| kernel.traceoff_on_warning    | 0      | Désactiver le suivi des traces lors d'avertissements |
| kernel.tracepoint_printk      | 0      | Imprimer les points de trace avec printk désactivé |
| kernel.unknown_nmi_panic      | 0      | Panique sur NMIs inconnus désactivée |
| kernel.unprivileged_bpf_disabled | 2   | Désactiver l'utilisation non privilégiée du BPF (2) |
| kernel.unprivileged_userns_apparmor_policy | 1   | Politiques d'AppArmor pour utilisateurs non privilégiés activées |
| kernel.unprivileged_userns_clone | 1    | Cloner des espaces de noms utilisateur non privilégiés activé |
| kernel.usermodehelper.bset    | 4294967295 511   | Bits spécifiques pour l'assistance utilisateur (4294967295, 511) |
| kernel.usermodehelper.inheritable | 4294967295 511   | Bits spécifiques hérités pour l'assistance utilisateur (4294967295, 511) |
| kernel.version                | #1 SMP PREEMPT_DYNAMIC Debian 6.12.74-2 (2026-03-08) | Version du noyau et configuration |
| kernel.warn_limit             | 0      | Limite d'avertissement désactivée |
| kernel.watchdog               | 1      | Détecteur de watchdog activé |
| kernel.watchdog_cpumask       | 0-3    | Masque de cœurs pour le détecteur de watchdog (tous les cœurs) |
| kernel.watchdog_thresh        | 10     | Durée maximale avant un avertissement du watchdog en secondes (10s) |
| kernel.yama.ptrace_scope      | 0      | Portée de l'interception ptrace désactivée |

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

| Paramètre                        | Valeur       | Description Simple |
|----------------------------------|-------------|--------------------|
| net.core.bpf_jit_enable          | 1           | Compilation JIT du BPF activée |
| net.core.bpf_jit_harden          | 0           | Durcissement de la compilation JIT désactivé |
| net.core.bpf_jit_kallsyms        | 1           | Afficher les symboles KALLSYMS lors de la compilation JIT |
| net.core.bpf_jit_limit           | 528482304    | Limite de l'espace d'exécution BPF (en octets) |
| net.core.busy_poll              | 0           | Nombre maximal de tentatives de polling des sockets occupées désactivé |
| net.core.busy_read              | 0           | Nombre maximal de lectures non-empêchées désactivé |
| net.core.default_qdisc          | fq_codel     | Défaut du disciplinnaire de queue : Codel |
| net.core.devconf_inherit_init_net | 0            | Hériter des configurations initiales de l'interface réseau désactivé |
| net.core.dev_weight             | 64          | Poids par défaut pour la gestion des paquets (en unités) |
| net.core.dev_weight_rx_bias     | 1           | Surpoids du poids RX sur TX lors de la répartition de la bande passante |
| net.core.dev_weight_tx_bias     | 1           | Surpoids du poids TX sur RX lors de la répartition de la bande passante |
| net.core.fb_tunnels_only_for_init_net | 0          | Tunnels de flux de données uniquement pour init_net désactivé |
| net.core.flow_limit_cpu_bitmap   | 0           | Masque CPU pour la limite de flux désactivé |
| net.core.flow_limit_table_len    | 4096        | Taille maximale du tableau de limites de flux (en entrées) |
| net.core.gro_normal_batch       | 8           | Batch normal de regroupement des paquets en GRO (Group Rewriting of Headers) |
| net.core.high_order_alloc_disable | 0          | Désactiver l'allocation d'ordre élevé désactivé |
| net.core.max_skb_frags          | 17         | Maximum du nombre de fragments de paquet (SKB) |
| net.core.mem_pcpu_rsv           | 256        | Taille de la réserve mémoire CPU spécifique (en pages) |
| net.core.message_burst         | 10         | Limite d'burst des messages système (nombre) |
| net.core.message_cost          | 5          | Coût de chaque message système (valeur) |
| net.core.netdev_budget         | 300        | Budjet par défaut pour les opérations réseau (en unités) |
| net.core.netdev_budget_usecs   | 8000       | Durée maximale du budget réseau en microsecondes |
| net.core.netdev_max_backlog    | 1000       | Taille maximale de la file d'attente pour le netdev (nombre) |
| net.core.netdev_rss_key        | 00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00 | Clé par défaut pour l'allocation RSS (RFS) |
| net.core.netdev_tstamp_prequeue | 1           | Pré-étiquetage de l'horodatage des paquets activé |
| net.core.netdev_unregister_timeout_secs | 10       | Durée maximale d'inactivité avant désinscription du périphérique réseau (en secondes) |
| net.core.optmem_max             | 131072      | Taille maximale de la mémoire optimisée (en octets) |
| net.core.rmem_default           | 212992      | Taille par défaut du buffer d'entrée réseau (en octets) |
| net.core.rmem_max               | 212992      | Taille maximale du buffer d'entrée réseau (en octets) |
| net.core.rps_default_mask       | 0           | Masque de base par défaut pour l'ingestion de flux RPS (Receive Packet Steering) désactivé |
| net.core.rps_sock_flow_entries  | 0           | Nombre maximal d'entrées de flux RPS par socket désactivé |
| net.core.skb_defer_max          | 64         | Durée maximale de la déferral des paquets (en unités) |
| net.core.somaxconn              | 4096        | Maximum du nombre d'connections simultanées maximales (socket) |
| net.core.tstamp_allow_data     | 1           | Autoriser les étiquettes horodatages sur les données activé |
| net.core.txrehash               | 1           | Réécrire le header de transmission activé |
| net.core.warnings               | 0           | Afficher des avertissements par défaut désactivés |
| net.core.wmem_default           | 212992      | Taille par défaut du buffer de sortie réseau (en octets) |
| net.core.wmem_max               | 212992      | Taille maximale du buffer de sortie réseau (en octets) |
| net.core.xfrm_acq_expires       | 30          | Durée d'expiration des acquisitions XFRM en secondes |
| net.core.xfrm_aevent_etime     | 10         | Durée d'événement d'exécution de l'agent de protection activé (en secondes) |
| net.core.xfrm_aevent_rseqth    | 2          | Seuil d'ordre de séquence pour l'agent de protection activé |
| net.core.xfrm_larval_drop      | 1           | Désactiver le traçage XFRM larval (pupille) désactivé |

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

| Paramètre                        | Valeur       | Description Simple |
|----------------------------------|-------------|--------------------|
| net.mptcp.add_addr_timeout      | 120         | Durée d'expiration de l'ajout d'un adresse MPTCP (en secondes) |
| net.mptcp.allow_join_initial_addr_port | 1          | Permettre la jonction à partir du premier élément de l'adresse activé |
| net.mptcp.available_schedulers  | default     | Types disponibles de planificateurs MPTCP : par défaut |
| net.mptcp.blackhole_timeout     | 3600        | Durée d'expiration du blackhole (en secondes) |
| net.mptcp.checksum_enabled      | 0           | Activer la vérification des sommets désactivé |
| net.mptcp.close_timeout         | 60          | Durée d'expiration de la fermeture (en secondes) |
| net.mptcp.enabled               | 1           | Activer MPTCP activé |
| net.mptcp.pm_type               | 0           | Type de gestionnaire de protocole MPTCP : par défaut désactivé |
| net.mptcp.scheduler             | default     | Planificateur MPTCP : par défaut |
| net.mptcp.stale_loss_cnt        | 4           | Nombre d'événements de perte inactifs avant de déclencher un événement de perte |
| net.nf_conntrack_max            | 65536       | Taille maximale de la table nf_conntrack (nombre) |
| net.unix.max_dgram_qlen         | 512         | Taille maximale de la file d'attente des datagrammes Unix (nombre) |

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

| Paramètre                        | Valeur       | Description Simple |
|----------------------------------|-------------|--------------------|
| user.max_cgroup_namespaces      | 14209       | Nombre maximum de namespaces cgroups (nombre) |
| user.max_fanotify_groups        | 128         | Taille maximale du groupe fanotify (nombre) |
| user.max_fanotify_marks         | 30834       | Taille maximale des marques fanotify (nombre) |
| user.max_inotify_instances      | 128         | Nombre maximum d'instances inotify (nombre) |
| user.max_inotify_watches        | 28977       | Nombre maximum de fichiers observés par inotify (nombre) |
| user.max_ipc_namespaces         | 14209       | Nombre maximum de namespaces IPC (nombre) |
| user.max_mnt_namespaces         | 14209       | Nombre maximum de namespaces mount (nombre) |
| user.max_net_namespaces         | 14209       | Nombre maximum de namespaces réseau (nombre) |
| user.max_pid_namespaces         | 14209       | Nombre maximum de namespaces PID (nombre) |
| user.max_time_namespaces        | 14209       | Nombre maximum de namespaces temps (nombre) |
| user.max_user_namespaces        | 14209       | Nombre maximum de namespaces utilisateurs (nombre) |
| user.max_uts_namespaces         | 14209       | Nombre maximum de namespaces UTS (nombre) |

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

| Paramètre                      | Valeur Actuelle | Description Simple                                                                  |
|-------------------------------|-----------------|--------------------------------------------------------------------------------------|
| vm.admin_reserve_kbytes       | 8192            | Réserve de mémoire administrative en kilo-octets.                                    |
| vm.compaction_proactiveness   | 20              | Niveau d'agressivité pour la compacité prédictive.                                   |
| vm.compact_unevictable_allowed| 1               | Autorise ou non l'éviction des pages inutilisables.                                  |
| vm.dirty_background_bytes     | 0               | Limite de tampon de fonds en mémoire sale (déprécié).                                |
| vm.dirty_background_ratio     | 10              | Pourcentage maximal du total de la mémoire qui peut être en état d'attente.          |
| vm.dirty_bytes                | 0               | Taille totale des pages mémoire sales.                                               |
| vm.dirty_expire_centisecs     | 3000            | Temps (en centi-secondes) avant l'expiration du tampon de fonds.                     |
| vm.dirty_ratio                | 20              | Pourcentage maximal de la mémoire physique qui peut être en état d'attente.          |
| vm.dirtytime_expire_seconds   | 43200           | Durée (en secondes) après laquelle les pages dirty sont considérées comme obsolètes. |
| vm.dirty_writeback_centisecs  | 500             | Temps (en centi-secondes) entre deux opérations de remplacement en écriture.         |
| vm.enable_soft_offline        | 1               | Active ou désactive le soft offline pour les interfaces réseau.                      |
| vm.extfrag_threshold          | 500             | Seuil d'éxtension des fragments mémoire.                                             |
| vm.hugetlb_optimize_vmemmap   | 0               | Optimise la mappage de la mémoire hugetlb.                                           |
| vm.hugetlb_shm_group          | 0               | Groupe de processus pour les objets hugetlb partagés.                                |
| vm.laptop_mode                | 0               | Mode d'ordinateur portable (0: désactivé).                                           |
| vm.legacy_va_layout           | 0               | Paramètre du layout des adresses virtuelles legacy.                                  |
| vm.lowmem_reserve_ratio       | 256 256 32 0 0  | Ratio de réservation de mémoire pour les zones basses.                               |
| vm.max_map_count              | 1048576         | Nombre maximal de maps (tableaux) autorisés par processus.                           |
| vm.memfd_noexec               | 0               | Autorise l'exécution des fichiers memfd.                                             |
| vm.memory_failure_early_kill  | 0               | Détruit les tâches en cas de défaillance mémoire précoce.                            |
| vm.memory_failure_recovery    | 1               | Permet la récupération après une défaillance de mémoire.                             |
| vm.min_free_kbytes            | 67584           | Nombre minimal de kilo-octets de libre à maintenir.                                  |
| vm.min_slab_ratio             | 5               | Ratio minimal de slab qui doit être disponible.                                      |
| vm.min_unmapped_ratio         | 1               | Ratio minimal de pages non mappées qui doivent être présentes.                       |
| vm.mmap_min_addr              | 65536           | Adresse minimale pour l'allocation mmap.                                             |
| vm.mmap_rnd_bits              | 28              | Bits de décalage aléatoire pour l'addressation mmap.                                 |
| vm.mmap_rnd_compat_bits       | 8               | Bits de décalage compatible pour l'addressation mmap.                                |
| vm.nr_hugepages               | 0               | Nombre de pages hugetlb en cache.                                                    |
| vm.nr_hugepages_mempolicy     | 0               | Nombre de pages hugetlb selon la politique de mémoire.                               |
| vm.nr_overcommit_hugepages    | 0               | Nombre total de pages hugetlb autorisées à l'overcommit.                             |
| vm.numa_stat                  | 1               | Affiche des statistiques NUMA (Node).                                                |
| vm.numa_zonelist_order        | Node            | Ordre des listes NUMA.                                                               |
| vm.oom_dump_tasks             | 1               | Filtre les tâches lors de la détection d'un OOM.                                     |
| vm.oom_kill_allocating_task   | 0               | Exécute l'OOM killer sur le processus en cours d'allocation.                         |
| vm.overcommit_kbytes          | 0               | Limite maximale d'overcommit en kilo-octets.                                         |
| vm.overcommit_memory          | 0               | Mode d'overcommit (0: strict).                                                       |
| vm.overcommit_ratio           | 50              | Pourcentage maximal de la mémoire physique qui peut être overcomitée.                |
| vm.page-cluster               | 3               | Groupe de pages à évacuer ensemble (3: normal).                                      |
| vm.page_lock_unfairness       | 5               | Facteur d'équité pour le verrouillage de page.                                       |
| vm.panic_on_oom               | 0               | Active ou désactive l'action panique en cas d'OOM.                                   |
| vm.percpu_pagelist_high_fraction| 0              | Fréquence maximale du pagelist percpu (0: non activée).                             |
| vm.stat_interval              | 1               | Intervalle de statistiques (en secondes).                                            |
| vm.swappiness                  | 60              | Niveau d'agressivité pour l'utilisation des pages swap.                             |
| vm.unprivileged_userfaultfd   | 0               | Autorise ou désactive les userfaultfd pour les utilisateurs non privilégiés.         |
| vm.user_reserve_kbytes        | 116915          | Réserve de mémoire utilisateur en kilo-octets.                                       |
| vm.vfs_cache_pressure         | 100             | Pression sur le cache VFS (100: équilibrée).                                         |
| vm.watermark_boost_factor     | 15000           | Facteur d'augmentation des marquages d'eau.                                          |
| vm.watermark_scale_factor     | 10              | Facteur de scaling pour les marquages d'eau.                                         |
| vm.zone_reclaim_mode          | 0               | Mode de récupération zone (0: normal).                                               |

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------






