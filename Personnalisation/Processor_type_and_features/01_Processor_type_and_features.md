------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# <p align='center'> Processor type and features </p>

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## A. Présentation
Ces options permettent de configurer le noyau pour prendre en charge différents types de processeurs et plateformes, ainsi que des fonctionnalités spécifiques pour améliorer les performances et la fiabilité du système.

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

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

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

<br />

### 22. Old AMD GART IOMMU support

<br />

### 23. Enable Maximum number of SMP Processors and NUMA Nodes

<br />

### 24. Maximum number of CPUs

<br />

### 25. Cluster scheduler support

<br />

### 26. Multi-core scheduler support
#### A. CPU core priorities scheduler support

### 27. Local APIC support on uniprocessors
#### A. IO-APIC support on uniprocessors

### 28. Reroute for broken boot IRQs

### 29. Machine Check / overheating reporting
#### A. Support for deprecated /dev/mcelog character device
#### B. Intel MCE features
#### C. AMD MCE features
#### D. Support for old Pentium 5 / WinChip machine checks

<br />

### 30. Machine check injector support

<br />

### 31. Legacy VM86 support

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 32. Enable support for 16-bit segments

<br />

### 33. Enable vsyscall emulation

<br />

### 34. IOPERM and IOPL Emulation

<br />

### 35. Toshiba Laptop support

<br />

### 36. Enable X86 board specific fixups for reboot

<br />

### 37. Late microcode loading (DANGEROUS)

<br />

### 38. Enforce late microcode loading minimal revision check
#### A. /dev/cpu/*/msr   - Model-specific register support
#### B. /dev/cpu/*/cpuid - CPU information support

<br />

### 39. High Memory Support
#### A. off
#### B. 4GB
#### C. 64GB

<br />

### 40. Memory split
#### A. 3G/1G user/kernel split
#### B. 3G/1G user/kernel split (for full 1G low memory)
#### C. 2G/2G user/kernel split
#### D. 2G/2G user/kernel split (for full 2G low memory)
#### E. 1G/3G user/kernel split

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 41. PAE (Physical Address Extension) Support

<br />

### 42. Enable 5-level page tables support

<br />

### 43. Enable statistic for Change Page Attribute

<br />

### 44. AMD Secure Memory Encryption (SME) support

<br />

### 45. NUMA Memory Allocation and Scheduler Support
#### A. old style AMD Opteron NUMA detection
#### B. ACPI NUMA detection
#### C. NUMA emulation

<br />


### 46. Maximum NUMA Nodes (as a power of 2)

<br />

### 47. Enable sysfs memory/probe interface

<br />

### 48. Support non-standard NVDIMMs and ADR protected memory

<br />

### 49. Allocate 3rd-level pagetables from highmem

<br />

### 50. Check for low memory corruption 

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 51. Set the default setting of memory_corruption_check

<br />

### 52. Math emulation

<br />

### 53. MTRR (Memory Type Range Register) support
#### A. MTRR cleanup support
#### B. MTRR cleanup enable value (0-1)
#### C. MTRR cleanup spare reg num (0-7)
#### D. x86 PAT support

### 54. User Mode Instruction Prevention

<br />

### 55. Indirect Branch Tracking

<br />

### 56. Memory Protection Keys

<br />

### 57. TSX enable mode
#### A. off
#### B. on
#### C. auto

<br />

### 58. Software Guard extensions (SGX)

<br />

### 59. X86 userspace shadow stack (NEW)

<br />

### 60. Intel Trust Domain Extensions (TDX) host support

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 61. EFI runtime service support
#### A. EFI stub support
#### A1. EFI handover protocol (DEPRECATED)
#### A2. EFI mixed-mode support
#### B1. Enable EFI fake memory map
#### B2. maximum allowable number of ranges in efi_fake_mem boot option
#### C1. Export EFI runtime maps to sysfs

<br />

### 62. Timer frequency
#### A. 100 HZ
#### B. 250 HZ
#### C. 300 HZ
#### D. 1000 HZ

<br />

### 63. Build a relocatable kernel
#### A. Randomize the address of the kernel image (KASLR)

<br />

### 64. Alignment value to which kernel should be aligned

<br />

### 65. Randomize the kernel memory sections Physical memory mapping padding

<br />

### 66. Linear Address Masking support (NEW)

<br />

### 67. Disable the 32-bit vDSO (needed for glibc 2.3.3)

### 68. vsyscall table for legacy applications
#### A. Emulate execution only
#### B. None

<br />

### 69. Built-in kernel command line
#### A. Built-in kernel command string
#### B. Built-in command line overrides boot loader arguments

<br />

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 70. Enable the LDT (local descriptor table)

<br />

### 71. Enforce strict size checking for sigaltstack

<br />

### 72. Kernel Live Patching

<br />
