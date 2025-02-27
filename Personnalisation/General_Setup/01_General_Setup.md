------------------------------------------------------------------------------------------------------------------------------------------
# <p align='center'> General Setup </p>
------------------------------------------------------------------------------------------------------------------------------------------
## A. Présentation

<br />

## B. Configuration
### 1. Compile also drivers which will not load [N]
Cette option permet de compiler les pilotes qui ne seront pas chargés par défaut. Cela peut être utile pour les développeurs de pilotes ou pour les utilisateurs qui veulent avoir accès à des pilotes expérimentaux.

<br />

### 2. Compile the kernel with warnings as errors [N]
Cette option permet de traiter les avertissements de compilation comme des erreurs. Cela signifie que si un avertissement est détecté pendant la compilation, la compilation sera arrêtée.

<br />

### 3. Compile test UAPI headers [Y] 
Lorsque vous compilez un noyau Linux, vous avez la possibilité de compiler les en-têtes UAPI (User API) pour les tester.

Les en-têtes UAPI sont des fichiers d'en-tête qui définissent les interfaces de programmation pour les applications utilisateurs. 

Ils fournissent les déclarations de fonctions, les structures de données et les constantes nécessaires pour utiliser les fonctionnalités du noyau.

L'option **Compile test UAPI headers** permet de compiler ces en-têtes UAPI pour vérifier leur cohérence et leur compatibilité avec le code du noyau. Cette étape est importante pour plusieurs raisons :

- Validation des en-têtes UAPI : La compilation des en-têtes UAPI permet de vérifier qu'ils sont corrects et cohérents avec le code du noyau. Cela aide à détecter les erreurs de syntaxe, les incohérences de déclaration et les problèmes de compatibilité.
- Détection des problèmes de compatibilité : La compilation des en-têtes UAPI permet de détecter les problèmes de compatibilité entre les différentes versions du noyau et les applications utilisateurs.
- Amélioration de la qualité du code : La compilation des en-têtes UAPI encourage les développeurs à écrire du code de haute qualité, car ils doivent s'assurer que les en-têtes UAPI sont corrects et cohérents.


Lorsque vous activez l'option **Compile test UAPI headers**, le processus de compilation du noyau effectue les étapes suivantes :
- Il compile les en-têtes UAPI pour les tester.
- Il vérifie la cohérence et la compatibilité des en-têtes UAPI avec le code du noyau.
- Il rapporte les erreurs et les avertissements rencontrés pendant la compilation des en-têtes UAPI.

<br />

### 4. Local Version - apprend to kernel release [Custom]
Cette option permet d'ajouter une chaîne de caractères personnalisée à la version du kernel. Cela peut être utile pour identifier une version personnalisée du kernel.

<br />

### 5. Automatically apprend version information to the version string [N]
Lorsqu'elle est activée, le noyau ajoutera automatiquement des informations de version à la chaîne de version du noyau. 

<br />

### 6. Build ID Salt [???]
Cette option permet de spécifier une valeur de **salt** pour le Build ID du kernel. Le Build ID est une valeur unique qui identifie une version spécifique du kernel.

<br />

### 7. Kernel compression mode [zstd]
Cette option permet de choisir le mode de compression du kernel. 

Les options disponibles sont : 
- Gzip  : X86 et x64
- Lzma  : Arm et ARM64
- Bzip2 :
- Xz    :
- Lzo   :
- Zstd  : Est très rapide pour compresser les données, ce qui est important pour les applications où la compression est effectuée en temps réel.

| Algorithme  | Temps de compression (s) | Temps de décompression (s) |
| ----------- | ------------------------ | -------------------------- |
| ZSTD        | 1.3 Sec                  | 0.5 Sec                    |
| Gzip        | 2.5 Sec                  | 1.2 Sec                    |

<br />

### 8. Default init path [/sbin/init]
Cette option permet de spécifier le chemin d'accès par défaut pour les fichiers d'initialisation du système.

<br />

### 9. Default Hostname [Debian]
Cette option permet de spécifier le nom d'hôte par défaut pour le système.

<br />

### 10. System V IPC [Y]
Cette option permet d'activer ou de désactiver les fonctionnalités de communication inter-processus (IPC) de System V.

<br />

### 11. POSIX Message queues [Y]
Cette option permet d'activer ou de désactiver les files d'attente de messages POSIX.

<br />

### 12. General notification queue [N]
Cette option permet d'activer ou de désactiver la file d'attente de notifications générales.

<br />

### 13. Enable process_vm_readv/writev_syscalls [Y]
Cette option permet d'activer ou de désactiver les appels système process_vm_readv et process_vm_writev.

<br />

### 14. uselib syscall (for libc5 and earlier) [N] (Risque de sécurité)
Cette option permet d'activer ou de désactiver l'appel système uselib pour les versions de libc antérieures à la 5.

<br />

### 15. Auditing support [???]
Cette option permet d'activer ou de désactiver la prise en charge de l'audit.

Recommandation: uselib à désactiver !

<br />

### 16. KUnit test for kernel/time functions

<br />

### 17. Preemption Model [Preemptible Kernel]
Cette option permet de choisir le modèle de préemption du kernel. 

Les options disponibles sont : 
- Preemptible Kernel (Low-Latency Desktop)
- Voluntary Kernel Preemption (Desktop)
- No Forced Preemption (Server)

<br />

### 18. Preemption behaviour defined on boot [Y]
Cette option permet de spécifier le comportement de préemption à l'amorçage.

- none      : désactive la préemption
- voluntary : active la préemption volontaire (No Forced Preemption)
- forced    : active la préemption forcée (Preemptible Kernel)
- rt        : active la préemption en temps réel (Preempt-RT)

<br />

### 19. Core Scheduling for SMT [Y]
Cette option permet d'activer ou de désactiver la planification des cœurs pour les processeurs SMT.

<br />

### 20. CPU Isolation [Y] (Amélioration Gain de performance significativement)
Cette option permet d'activer ou de désactiver l'isolation des processeurs.

<br />

### 21. Kernel .config support [M + Y]
Cette option permet d'activer ou de désactiver la prise en charge du fichier de configuration du kernel.

> Enable Access to .config throught /proc/config/gz : Permet de créer un fichier compresser contenant le paramétrage du Kernel.

<br />

### 22. Enable kernel headers throught /sys/kernel/kheaders.tar.xz [N]
Cette option permet d'activer ou de désactiver l'accès aux en-têtes du kernel à travers le fichier /sys/kernel/kheaders.tar.xz.

<br />

### 23. Kernel log buffer size [12] (Valeur par défaut: 17)
Cette option permet de spécifier la taille du tampon de journalisation du kernel.

[ChatGPT] : Pour une journée de log théorique, mettre la valeur sur 12.

<br />

### 24. CPU Kernel log buffer size contribution [12]
Cette option permet de spécifier la contribution de chaque processeur à la taille du tampon de journalisation du kernel.

<br />

### 25. Printk indexing debugfs interface [Y] (Message Kernel !)
Cette option permet d'activer ou de désactiver l'interface de débogage printk.

<br />

### 26. Memory placement award NUMA scheduler [Y + Y]
Cette option permet d'activer ou de désactiver la prise en compte de la placement de la mémoire pour les planificateurs NUMA.

> Automatically enable NUMA aware memory/task placement

<br />

### 27. Checkpoint/restore support [Y] (Permet de capturer un proces pour le relancer)
Cette option permet d'activer ou de désactiver la prise en charge de la sauvegarde et de la restauration des processus.

```bash
clear;

DATE=$(date +'%Y%m%d%H%M%S')

# Sauvegarde du processus avec l'ID 1234 (Ne ferme pas le processus)
checkpoint -c 1234 checkpoint_file;
checkpoint -c 1234 $DATE;

# Sauvegarde du processus avec l'ID 1234 (Ferme le processus à la fin)
checkpoint -c my_checkpoint -k 1234;
checkpoint -c $DATE -k 1234;

# Restauration du processus à partir du fichier de sauvegarde
restore -r checkpoint_file;
restore -r $DATE;
```

<br />

### 28. Automatic process group scheduling [Y]
Cette option permet d'activer ou de désactiver la planification automatique des groupes de processus.

<br />

### 29. Kernel -> user space relay support [Y] (Utile pour le debuggage)
Cette option permet d'activer ou de désactiver la prise en charge du relais entre le kernel et l'espace utilisateur.

<br />

### 30. Initial Ram filesystem and RAM disk (initramfs/initrd) support [Y] (Mitigé)
Cette option permet de compiler le support pour les systèmes de fichiers et les disques RAM initiaux (initramfs/initrd).

Un système de fichiers RAM initial est une archive compressée qui contient les fichiers nécessaires pour démarrer le système, tandis qu'un disque RAM est un espace de stockage temporaire utilisé pendant le démarrage.

Si vous activez cette option, vous pourrez utiliser des systèmes de fichiers et des disques RAM initiaux pour démarrer votre système.

#### 30A. Ignore the initramfs passed bu the bootloader
#### 30B. User  ID to map to 0 (user root) (NEW)
#### 30C. Group ID to map to 0 (user root) (NEW)
#### 30D. Support initial ramdisk/ramfs compressed using gzip
#### 30E. Support initial ramdisk/ramfs compressed using bzip2
#### 30F. Support initial ramdisk/ramfs compressed using LZMA
#### 30G. Support initial ramdisk/ramfs compressed using XZ
#### 30H. Support initial ramdisk/ramfs compressed using LZO
#### 30I. Support initial ramdisk/ramfs compressed using LZ4
#### 30J. Support initial ramdisk/ramfs compressed using ZSTD

<br />

### 31. Boot config support [Y]
Cette option permet de compiler le support pour les configurations de démarrage.

Les configurations de démarrage définissent les paramètres de démarrage du système, tels que les options de noyau, les paramètres de l'interface réseau, etc.

Si vous activez cette option, vous pourrez utiliser des configurations de démarrage personnalisées pour démarrer votre système.

#### 31A. Force Unconditional bootconfig processing (New)
#### 31B. Embed bootconfig file in the kernel
#### 31C. Embedded bootconfig file path


**/boot/bootconfig**
```
# Fichier bootconfig exemple

# Options de démarrage CPU
cpu.max_cstate=1
cpu.min_cstate=0
cpu.governor=performance
cpu.energy_performance_preference=balance_performance

# Options de démarrage de la gestion de l'énergie
power.management.enabled=1
power.management.policy=balance_performance

# Options de démarrage de la planification des tâches
sched.sched_latency_ns=100000
sched.sched_migration_cost_ns=500000
```

| Parametre                          | Valeur              | Description                                                                                |
| ---------------------------------- | ------------------- | ---------------------------------------------------------------------------------          |
| cpu.max_cstate                     | 0                   | Désactive la mise en veille                                                                |
| cpu.max_cstate                     | 1                   | Niveau de mise en veille léger (C1)                                                        |
| cpu.max_cstate                     | 2                   | Niveau de mise en veille moyen (C2)                                                        |
| cpu.max_cstate                     | 3                   | Niveau de mise en veille profond (C3)                                                      |
| cpu.max_cstate                     | 4                   | Niveau de mise en veille très profond (C4)                                                 |
| ---------------------------------- | ------------------- | ---------------------------------------------------------------------------------          |
| cpu.min_cstate                     | 0                   | niveau minimal de mise en veille du CPU                                                    |
| ---------------------------------- | ------------------- | ---------------------------------------------------------------------------------          |
| cpu.governor                       | performance         | Priorise les performances et maintient la fréquence d'horloge la plus élevée possible      |
| cpu.governor                       | powersave           | Priorise la consommation d'énergie et réduit la fréquence d'horloge                        |
| cpu.governor                       | ondemand            | Ajuste la fréquence d'horloge en fonction de la charge du système                          |
| cpu.governor                       | conservative        | Ajuste la fréquence d'horloge en fonction de la charge du système. (Meilleur cons.)        |
| ---------------------------------- | ------------------- | ---------------------------------------------------------------------------------          |
| cpu.energy_performance_preference  | balance_performance | Equilibre entre les performances et la consommation d'énergie                              |
| cpu.energy_performance_preference  | performance         | Priorise les performances                                                                  |
| cpu.energy_performance_preference  | power               | Priorise la consommation d'énergie                                                         |
| ---------------------------------- | ------------------- | ---------------------------------------------------------------------------------          |
| power.management.enabled           | 0                   | Désactive la gestion de l'énergie                                                          |
| power.management.enabled           | 1                   | Active la gestion de l'énergie                                                             |
| ---------------------------------- | ------------------- | ---------------------------------------------------------------------------------          |
| power.management.policy            | balance_performance | Equilibre entre les performances et la consommation d'énergie                              |
| power.management.policy            | performance         | Priorise les performances                                                                  |
| power.management.policy            | power               | Priorise la consommation d'énergie                                                         |
| ---------------------------------- | ------------------- | ---------------------------------------------------------------------------------          |
| sched.sched_latency_ns             | 100000              | Définit la latence de planification des tâches en nanosecondes.                            |
| sched.sched_migration_cost_ns      | 500000              | Définit le coût de migration des tâches en nanosecondes.                                   |
| ---------------------------------- | ------------------- | ---------------------------------------------------------------------------------          |

<br />

### 32. Preserve cpio archive mtimes in intiramfs [Y]
Cette option permet de conserver les dates de modification (mtimes) des archives cpio dans les systèmes de fichiers RAM initiaux (initramfs).

Les archives cpio sont utilisées pour stocker les fichiers dans les systèmes de fichiers RAM initiaux.

Si vous activez cette option, les dates de modification des archives cpio seront conservées dans les systèmes de fichiers RAM initiaux.

<br />

### 33. Compiler optimisation level [-o2]
Cette option permet de définir le niveau d'optimisation du compilateur pour la compilation du noyau. 

Les niveaux d'optimisation définissent la quantité d'optimisation effectuée par le compilateur pour améliorer les performances du code généré. 

Les niveaux d'optimisation les plus courants sont :

-O0 : pas d'optimisation   : Débogage

-O1 : optimisation légère  : Compressé

-O2 : optimisation moyenne : Stabilité

-O3 : optimisation élevée  : Performance

<br />

### 34. Profiling support [Y]
Cette option permet de compiler le support pour le profilage.

Le profilage est une technique qui permet de mesurer les performances du code en cours d'exécution.

Si vous activez cette option, vous pourrez utiliser des outils de profilage pour analyser les performances de votre noyau.

```
Oprofile : Oprofile est un outil de profilage qui permet de collecter des informations sur les performances du kernel. Lorsque Oprofile est activé, le kernel collecte des informations sur les fonctions et les lignes de code qui sont exécutées, ainsi que sur le temps passé dans chaque fonction.

Kprobes : Kprobes est un outil de profilage qui permet de collecter des informations sur les performances du kernel en utilisant des sondes de profilage. Les sondes de profilage sont des points d'entrée dans le code qui permettent de collecter des informations sur les performances du kernel.

Ftrace : Ftrace est un outil de profilage qui permet de collecter des informations sur les performances du kernel en utilisant des traces de fonction. Les traces de fonction permettent de suivre l'exécution des fonctions dans le kernel et de collecter des informations sur les performances du kernel.
```

☐ ☑
