------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# <p align='center'> Processor type and features </p>

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## A. Présentation
Ces options permettent de configurer le noyau pour prendre en charge différents types de processeurs et plateformes, ainsi que des fonctionnalités spécifiques pour améliorer les performances et la fiabilité du système.

Ces options permettent au noyau de prendre en charge divers composants matériels, de gérer les ressources système, et de fournir des fonctionnalités supplémentaires pour les performances et la fiabilité du système.


**EN COURS**

<br />

## B. Configuration
### 01. Symmetric multi-processing support
Permet d'activer le support pour les systèmes multiprocesseurs symétriques (SMP).

Les systèmes SMP sont des ordinateurs qui utilisent plusieurs processeurs pour exécuter des tâches en parallèle, ce qui peut améliorer les performances globales du système.

<br />

### 02. Support x2apic
Permet d'activer le support pour les processeurs x86 qui utilisent l'interface x2apic pour gérer les interruptions.

x2apic est une extension de l'interface APIC (Advanced Programmable Interrupt Controller) qui permet de gérer les interruptions de manière plus efficace.

<br />

### 03. Enable MSI and MSI-x delivery by posted interrupts (NEW)
Permet d'activer la livraison de messages d'interruption (MSI) et de messages d'interruption étendus (MSI-x) par les interruptions postées.

Les interruptions postées sont une fonctionnalité qui permet de réduire la charge de travail du processeur en traitant les interruptions de manière plus efficace.

<br />

### 04. Enable MPS table
Permet d'activer la table MPS qui contient des informations sur les processeurs présents dans le système. Cette table est utilisée pour gérer les processeurs et les interruptions.

<br />

### 05. x86 CPU resource control support
Permet d'activer le support pour le contrôle des ressources CPU x86.

Cette fonctionnalité permet de gérer les ressources CPU, telles que les registres et les caches, pour améliorer les performances du système.

<br />

### 06. Flexible Return and Event Delivery (NEW)
Permet d'activer la livraison flexible des événements et des retours.

Cette fonctionnalité permet de gérer les événements et les retours de manière plus efficace, ce qui peut améliorer les performances du système.

<br />

### 07. Support for big SMP systems with more than 8 CPUs
Permet d'activer le support pour les systèmes SMP avec plus de 8 processeurs.

Les systèmes SMP avec un grand nombre de processeurs nécessitent des fonctionnalités spécifiques pour gérer les processeurs et les interruptions.

<br />

### 08. Support for extended (non-PC) x86 platforms
Permet d'activer le support pour les plates-formes x86 étendues (non-PC).

Les plates-formes x86 étendues sont des systèmes qui utilisent des processeurs x86 mais qui ne sont pas des ordinateurs personnels.

#### A. Numascale NumaChip
Permet d'activer le support pour les systèmes Numascale NumaChip.
#### B. ScaleMP VSMP
Permet d'activer le support pour les systèmes ScaleMP VSMP.
#### C. SGI Ultraviolet
Permet d'activer le support pour les systèmes SGI Ultraviolet.
#### D. Goldfish (Virtual Platform)
Permet d'activer le support pour les systèmes Goldfish (Virtual Platform).
#### E. CE4100 TV platform
Permet d'activer le support pour les systèmes CE4100 TV platform.

#### F. Intel MID platform support
Permet d'activer le support pour les systèmes Intel MID platform.

#### G. Intel Quark platform support 
Permet d'activer le support pour les systèmes Intel Quark platform.


<br />

### 09. Intel Low Power Subsystem Support
Permet d'activer le support pour les sous-systèmes à faible consommation d'énergie Intel. Les sous-systèmes à faible consommation d'énergie sont des composants qui permettent de réduire la consommation d'énergie du système.

<br />

### 10. AMD ACPI2Platform devices support
Permet d'activer le support pour les périphériques AMD ACPI2Platform. Les périphériques ACPI2Platform sont des composants qui permettent de gérer les périphériques du système.

<br />

### 11. Intel SoC IOSF Sideband support for SoC platforms
Permet d'activer l'accès aux ressources de la plateforme SoC (System on Chip) Intel via le système de fichiers debugfs. Cela peut être utile pour les développeurs qui souhaitent accéder à ces ressources pour des raisons de débogage ou de développement.

#### A. Enable IOSF sideband access through debugfs
Permet d'activer l'accès aux ressources de la plateforme SoC Intel via le système de fichiers debugfs.

<br />

### 12. RDC R-321x SoC
Permet de prendre en charge les processeurs RDC R-321x SoC.

<br />

### 13. Support non-standard 32-bit
Permet de prendre en charge les processeurs 32 bits non standard.

<br />

### 14. SMP architectures [] (AMD)
Permet de prendre en charge les architectures SMP (Symmetric Multi-Processing), qui permettent de partager les ressources entre plusieurs processeurs.

<br />

### 15. STA2X11 Companion Chip Support
Permet de prendre en charge les puces STA2X11 Companion Chip.

<br />

### 16. Eurobraille/Iris poweroff module
Permet de prendre en charge le module de extinction de puissance Eurobraille/Iris.

<br />

### 17. Single-depth WCHAN output
Permet de configurer la sortie WCHAN (Wait Channel) pour afficher uniquement les informations de niveau supérieur.

<br />

### 18. Processor Family
Permet de sélectionner la famille de processeurs à prendre en charge.

#### XX. Generic-x86-64 [X]
Prend en charge les processeurs x86-64 génériques.

#### A. 486SX
Prend en charge les processeurs 486SX.

#### B. 486DX
Prend en charge les processeurs 486DX.

#### C. 586/K5/5x86/6x86/6x86MX
Prend en charge les processeurs  586, K5, 5x86, 6x86, 6x86MX.

#### D. Pentium-Classic
Prend en charge les processeurs Pentium classiques.

#### E. Pentium-MMX
Prend en charge les processeurs Pentium avec instruction MMX.

#### F. Pentium-Pro
Prend en charge les processeurs Pentium Pro.

#### G. Pentium-II/Celeron(pre-Coppermine)
Prend en charge les processeurs Pentium II et Celeron (avant Coppermine).

#### H. Pentium-III/Celeron(Coppermine)/Pentium-III Xeon
Prend en charge les processeurs  Pentium III, Celeron (Coppermine) et Pentium III Xeon.

#### I. Pentium M
Prend en charge les processeurs Pentium M.

#### J. Pentium-4/Celeron(P4-based)/Pentium-4 M/older Xeon
Prend en charge les processeurs Pentium 4, Celeron (basé sur P4), Pentium 4 M et Xeon plus anciens.

#### K. K6/K6-II/K6-III
Prend en charge les processeurs K6, K6-II et K6-III.

#### L. Athlon/Duron/K7
Prend en charge les processeurs Athlon, Duron et K7.

#### M. Opteron/Athlon64/Hammer/K8
Prend en charge les processeurs Opteron, Athlon 64, Hammer et K8.

#### N. Crusoe
Prend en charge les processeurs Crusoe.

#### O. Efficeon
Prend en charge les processeurs Efficeon.

#### P. Winchip-C6
Prend en charge les processeurs Winchip-C6.

#### Q. Winchip-2/Winchip-2A/Winchip-3
Prend en charge les processeurs Winchip-2, Winchip-2A et Winchip-3.

#### R. AMD Elan
Prend en charge les processeurs AMD Elan.

#### S. GeodeGX1
Prend en charge les processeurs Geode GX1.

#### T. Geode GX/LX
Prend en charge les processeurs Geode GX et LX.

#### U. CyrixIII/VIA-C3
Prend en charge les processeurs Cyrix III et VIA C3.

#### V. VIA C3-2 (Nehemiah)
Prend en charge les processeurs

#### W. VIA C7
Prend en charge les processeurs

#### X. Intel P4 / older Netburst based Xeon
Prend en charge les processeurs

#### Y. Core 2/newer Xeon
Prend en charge les processeurs

#### Z. Intel Atom
Prend en charge les processeurs

<br />

### 19. Generic x86 support
Permet de prendre en charge les processeurs x86 génériques, ce qui signifie que le noyau pourra fonctionner sur une grande variété de processeurs x86, même si le processeur spécifique n'est pas explicitement pris en charge par une autre option.

<br />

### 20. HPET Timer Support
Permet de prendre en charge le timer HPET (High Precision Event Timer), qui est un timer matériel qui fournit une précision élevée pour les événements temporisés.

Cela peut être utile pour les applications qui nécessitent une synchronisation précise, comme les systèmes de temps réel ou les applications multimédia.

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 21. Enable DMI scanning
Permet au noyau de scanner les tables d'interface de gestion de bureau (DMI), qui contiennent des informations sur les composants matériels du système, tels que la carte mère, le BIOS et les périphériques.

Ces informations peuvent être utilisées par le noyau pour optimiser les performances du système et configurer les appareils matériels.

<br />

### 22. Old AMD GART IOMMU support
Active le support pour l'ancienne architecture IOMMU GART (Graphics Aperture Remapping Table) d'AMD.

GART est une technologie utilisée par AMD pour gérer l'accès à la mémoire pour les appareils graphiques.

Cette option est uniquement pertinente pour les anciens systèmes AMD.

<br />

### 23. Enable Maximum number of SMP Processors and NUMA Nodes
Permet au noyau de prendre en charge un nombre maximum de processeurs Symmetric Multi-Processing (SMP) et de nœuds Non-Uniform Memory Access (NUMA).

SMP permet à plusieurs processeurs de travailler ensemble pour améliorer les performances du système, tandis que NUMA est une architecture de mémoire qui permet à plusieurs processeurs d'accéder à une mémoire partagée.

<br />

### 24. Maximum number of CPUs
Définit le nombre maximum de CPU que le noyau peut prendre en charge.

Cette valeur doit être définie sur le nombre de CPU présents dans le système.

<br />

### 25. Cluster scheduler support
Active le support du planificateur de cluster, qui est un algorithme de planification qui groupe les tâches en clusters pour améliorer les performances du système et la scalabilité.

<br />

### 26. Multi-core scheduler support
Active le support du planificateur multi-cœur, qui permet au noyau de planifier les tâches sur plusieurs cœurs de CPU pour améliorer les performances du système.

#### A. CPU core priorities scheduler support
Active le support des priorités de cœur de CPU, qui permet au noyau de prioriser les tâches en fonction de leur importance et de les allouer à des cœurs de CPU spécifiques.

<br />

### 27. Local APIC support on uniprocessors
Active le support de l'APIC local (Advanced Programmable Interrupt Controller) sur les systèmes uniprocessor.

L'APIC est un circuit qui gère les interruptions et est utilisé pour gérer les interruptions du système.

#### A. IO-APIC support on uniprocessors
Active le support de l'IO-APIC (I/O Advanced Programmable Interrupt Controller) sur les systèmes uniprocessor.

L'IO-APIC est un circuit qui gère les interruptions d'entrée/sortie et est utilisé pour gérer les opérations d'entrée/sortie.

<br />

### 28. Reroute for broken boot IRQs
Permet au noyau de réacheminer les IRQ de démarrage cassés vers un IRQ fonctionnel. Cela est utile pour les systèmes avec des IRQ cassés ou non fonctionnels.

<br />

### 29. Machine Check / overheating reporting
Active le rapport d'erreurs de machine, qui sont des erreurs qui se produisent lorsque le CPU détecte une erreur matérielle.

Cette option active également le rapport de surchauffe, qui permet au noyau de détecter et de signaler la surchauffe du système.

#### A. Support for deprecated /dev/mcelog character device
Active le support du périphérique de caractère /dev/mcelog obsolète, qui est utilisé pour enregistrer les événements d'erreurs de machine.

#### B. Intel MCE features
Active le support des fonctionnalités MCE (Machine Check) d'Intel, qui fournissent des informations supplémentaires sur les erreurs de machine.

#### C. AMD MCE features
Active le support des fonctionnalités MCE d'AMD, qui fournissent des informations supplémentaires sur les erreurs de machine.

#### D. Support for old Pentium 5 / WinChip machine checks
Active le support des erreurs de machine sur les anciens systèmes Pentium 5 et WinChip.


<br />

### 30. Machine check injector support
Active le support de l'injecteur d'erreurs de machine, qui est un outil qui simule des erreurs de machine pour les tests et le débogage.

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 31. Legacy VM86 support
Active le support pour les anciennes applications VM86, qui utilisent des instructions 8086 pour accéder à la mémoire.

<br />

### 32. Enable support for 16-bit segments
Active le support pour les segments de 16 bits, qui sont utilisés par les anciennes applications pour accéder à la mémoire.

<br />

### 33. Enable vsyscall emulation
Active l'émulation des appels système virtuels, qui permettent aux applications de faire des appels système sans avoir à passer par la table des descripteurs de segments.

<br />

### 34. IOPERM and IOPL Emulation
Active l'émulation des opérations d'entrée/sortie et des niveaux de priorité d'entrée/sortie, qui permettent aux applications de contrôler les opérations d'entrée/sortie.

<br />

### 35. Toshiba Laptop support
Active le support pour les ordinateurs portables Toshiba, qui nécessitent des pilotes spécifiques pour fonctionner correctement.

<br />

### 36. Enable X86 board specific fixups for reboot
Active les corrections spécifiques au matériel pour le redémarrage, qui permettent au noyau de redémarrer correctement sur les systèmes x86.

<br />

### 37. Late microcode loading (DANGEROUS)
Ative le chargement tardif du microcode, qui peut être dangereux car il peut causer des problèmes de stabilité du système.

<br />

### 38. Enforce late microcode loading minimal revision check
Active la vérification de la révision minimale du microcode lors du chargement tardif, pour s'assurer que le microcode est compatible avec le système.

#### A. /dev/cpu/*/msr   - Model-specific register support
Active le support pour les registres spécifiques au modèle de processeur, qui permettent d'accéder à des fonctionnalités spécifiques du processeur.

#### B. /dev/cpu/*/cpuid - CPU information support
Active le support pour les informations sur le processeur, qui permettent d'accéder à des informations sur le processeur.

<br />

### 39. High Memory Support
Active le support pour la mémoire haute, qui permet au noyau d'accéder à des adresses de mémoire élevées.

#### A. off
Définit la taille de la mémoire haute que le noyau peut utiliser.

#### B. 4GB
Définit la taille de la mémoire haute que le noyau peut utiliser.

#### C. 64GB
Définit la taille de la mémoire haute que le noyau peut utiliser.

<br />

### 40. Memory split
Définit la façon dont la mémoire est partagée entre l'espace utilisateur et l'espace noyau.

L'option "for full 1G low memory" signifie que les 1 Go d'espace noyau sont réservés pour la mémoire basse (low memory), qui est la partie de la mémoire qui est accessible directement par le processeur sans avoir à passer par la mémoire virtuelle.

#### A. 3G/1G user/kernel split
3 Go pour l'espace utilisateur (applications et données)
1 Go pour l'espace noyau (code du noyau et données du noyau)

#### B. 3G/1G user/kernel split (for full 1G low memory)
3 Go pour l'espace utilisateur (applications et données)
1 Go pour l'espace noyau (code du noyau et données du noyau)

#### C. 2G/2G user/kernel split
2 Go pour l'espace utilisateur (applications et données)
2 Go pour l'espace noyau (code du noyau et données du noyau)

#### D. 2G/2G user/kernel split (for full 2G low memory)
2 Go pour l'espace utilisateur (applications et données)
2 Go pour l'espace noyau (code du noyau et données du noyau)

#### E. 1G/3G user/kernel split
1 Go pour l'espace utilisateur (applications et données)
3 Go pour l'espace noyau (code du noyau et données du noyau)

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 41. PAE (Physical Address Extension) Support
Active le support pour l'extension d'adresse physique, qui permet au noyau d'accéder à des adresses de mémoire plus élevées.

<br />

### 42. Enable 5-level page tables support
Active le support pour les tables de pages à 5 niveaux, qui permettent au noyau de gérer des adresses de mémoire plus élevées.

<br />

### 43. Enable statistic for Change Page Attribute
Active la collecte de statistiques sur les modifications des attributs de page, qui permettent d'améliorer les performances du système.

<br />

### 44. AMD Secure Memory Encryption (SME) support
Active le support pour la mémoire sécurisée par cryptographie d'AMD, qui permet de protéger la mémoire contre les attaques malveillantes.

<br />

### 45. NUMA Memory Allocation and Scheduler Support
Active le support pour l'allocation de mémoire et la planification de la mémoire non uniforme, qui permettent d'améliorer les performances du système sur les systèmes à plusieurs processeurs.

#### A. old style AMD Opteron NUMA detection
Méthode de détection héritée pour les processeurs AMD Opteron.

#### B. ACPI NUMA detection
Méthode de détection utilisant les informations ACPI (Advanced Configuration and Power Interface).

#### C. NUMA emulation
Émulation de NUMA pour les systèmes qui ne le supportent pas nativement.

<br />

### 46. Maximum NUMA Nodes (as a power of 2)
Définit le nombre maximum de noeuds NUMA que le noyau peut gérer. La valeur doit être une puissance de 2 (par exemple, 2, 4, 8, etc.).

<br />

### 47. Enable sysfs memory/probe interface
Active l'interface sysfs pour la mémoire et la sonde de mémoire.

<br />

### 48. Support non-standard NVDIMMs and ADR protected memory
Ajoute le support pour les NVDIMMs (Non-Volatile Dual In-Line Memory Module) non standard et la mémoire protégée par ADR (Address Range Decoder).

<br />

### 49. Allocate 3rd-level pagetables from highmem
Alloue les tables de pagination de 3e niveau à partir de la mémoire haute (highmem).

<br />

### 50. Check for low memory corruption 
Vérifie la corruption de la mémoire basse.

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 51. Set the default setting of memory_corruption_check
Définit la valeur par défaut pour la vérification de la corruption de la mémoire.

<br />

### 52. Math emulation
Active l'émulation des opérations mathématiques.

<br />

### 53. MTRR (Memory Type Range Register) support
Ajoute le support pour les registres MTRR :

#### A. MTRR cleanup support
Nettoyage des registres MTRR.

#### B. MTRR cleanup enable value (0-1)
Valeur d'activation du nettoyage des registres MTRR.

#### C. MTRR cleanup spare reg num (0-7)
Nombre de registres MTRR de réserve.

#### D. x86 PAT support
Support pour les tables de pagination PAT (Page Attribute Table).

<br />

### 54. User Mode Instruction Prevention
Empêche l'exécution d'instructions en mode utilisateur.

<br />

### 55. Indirect Branch Tracking
Suivi des branchements indirects.

<br />

### 56. Memory Protection Keys
Clés de protection de la mémoire.

<br />

### 57. TSX enable mode
Mode d'activation de la technologie TSX (Transactional Synchronization Extensions) :

<br />

### 58. Software Guard extensions (SGX)
Extensions de sécurité logicielle SGX.

<br />

### 59. X86 userspace shadow stack (NEW)
Pile d'ombre utilisateur x86 (nouvelle fonctionnalité).

<br />

### 60. Intel Trust Domain Extensions (TDX) host support
Support hôte pour les extensions de domaine de confiance Intel TDX.

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 61. EFI runtime service support
Support pour les services d'exécution EFI :

#### A. EFI stub support
Support pour les stubs EFI.

#### A1. EFI handover protocol (DEPRECATED)
Protocole de remise EFI (déprécié).

#### A2. EFI mixed-mode support
Support pour le mode mixte EFI.

#### B1. Enable EFI fake memory map
Activation de la carte mémoire EFI factice.
#### B2. maximum allowable number of ranges in efi_fake_mem boot option
Nombre maximum de plages autorisées dans l'option de démarrage efi_fake_mem.

#### C1. Export EFI runtime maps to sysfs
Exportation des cartes d'exécution EFI vers sysfs.

<br />

### 62. Timer frequency
Fréquence du timer.

#### A. 100 HZ
#### B. 250 HZ
#### C. 300 HZ
#### D. 1000 HZ

<br />

### 63. Build a relocatable kernel
Construction d'un noyau relocalisable.

#### A. Randomize the address of the kernel image (KASLR)
Randomisation de l'adresse de l'image du noyau.

<br />

### 64. Alignment value to which kernel should be aligned
Valeur d'alignement pour le noyau.

<br />

### 65. Randomize the kernel memory sections Physical memory mapping padding
Randomisation des sections de mémoire du noyau et padding de la carte mémoire.

Cette option permet de randomiser les sections de mémoire du noyau et d'ajouter un padding à la carte mémoire pour améliorer la sécurité.

<br />

### 66. Linear Address Masking support (NEW)
Support pour le masquage d'adresses linéaires (nouvelle fonctionnalité).

Cette option permet d'activer le masquage d'adresses linéaires, ce qui peut améliorer la sécurité en limitant l'accès à certaines régions de la mémoire.

<br />

### 67. Disable the 32-bit vDSO (needed for glibc 2.3.3)
Désactivation de la vDSO 32 bits (requise pour glibc 2.3.3).

Cette option permet de désactiver la vDSO 32 bits, ce qui peut être nécessaire pour certaines versions de la bibliothèque glibc.

<br />
 
### 68. vsyscall table for legacy applications
Table de vsyscall pour les applications héritées.

Cette option permet d'activer la table de vsyscall pour les applications héritées, ce qui peut améliorer la compatibilité avec les anciennes applications.

#### A. Emulate execution only
Émulation de l'exécution uniquement.

#### B. None
Aucune action

<br />

### 69. Built-in kernel command line
Ligne de commande du noyau intégrée. Cette option permet de spécifier une ligne de commande du noyau intégrée, ce qui peut être utile pour les systèmes embarqués ou les systèmes qui ne disposent pas d'un chargeur de démarrage.

#### A. Built-in kernel command string
Chaîne de commande du noyau intégrée.

#### B. Built-in command line overrides boot loader arguments
La ligne de commande intégrée remplace les arguments du chargeur de démarrage.

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 70. Enable the LDT (local descriptor table)
Active la table des descripteurs locaux (LDT), qui permet de définir des segments de mémoire pour les processus.

<br />

### 71. Enforce strict size checking for sigaltstack
Impose une vérification stricte de la taille pour les piles de signaux (sigaltstack), ce qui peut aider à détecter et à prévenir les erreurs de mémoire.

<br />

### 72. Kernel Live Patching
Active la mise à jour en direct du noyau (Kernel Live Patching), qui permet d'appliquer des correctifs de sécurité sans redémarrer le système.

<br />
