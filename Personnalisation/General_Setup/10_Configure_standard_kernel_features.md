---------------------------------------------------------------------------------
# <p align='center'> Configure standard kernel features </p>
---------------------------------------------------------------------------------
### A. Présentation
Ces options activent divers appels système, interfaces et fonctionnalités qui permettent aux applications d'interagir avec le noyau et d'accéder à diverses ressources système.

Ils activent également des outils de débogage et d'analyse qui aident les développeurs à déboguer et à optimiser le code du noyau.

<br />

### B. Configuration
#### 1. Enable 16-bit UID system calls
Permet d'activer les appels système UID 16 bits.

Les UID (User ID) sont des identifiants uniques attribués à chaque utilisateur du système.

Les appels système UID 16 bits permettent de gérer les utilisateurs et les groupes avec des identifiants plus petits, ce qui peut être utile pour les systèmes embarqués ou les systèmes anciens.

<br />

#### 2. Multiple users, groups and capabilities support
Permet de prendre en charge plusieurs utilisateurs, groupes et capacités.

Les capacités sont des autorisations spécifiques qui peuvent être attribuées à des utilisateurs ou des groupes pour leur permettre d'accéder à certaines ressources système.

Cette option permet de gérer de manière plus fine les autorisations et les accès aux ressources système.

<br />

#### 3. sgetmask/ssetmask syscalls support
Permet de prendre en charge les appels système sgetmask et ssetmask.

Ces appels système permettent de gérer les masques de signal, qui définissent les signaux que les processus peuvent recevoir.

<br />

#### 4. Sysfs syscall support
Permet de prendre en charge les appels système Sysfs.

Sysfs est un système de fichiers virtuel qui fournit des informations sur les périphériques et les ressources système.

Les appels système Sysfs permettent d'accéder à ces informations et de les modifier.

<br />

#### 5. open by fhandle syscalls
Permet de prendre en charge les appels système open by fhandle.

Ces appels système permettent d'ouvrir des fichiers en utilisant des descripteurs de fichier (fhandle) au lieu de noms de fichiers.

<br />

#### 6. Posix Clocks & timers
Permet de prendre en charge les horloges et les minuteries POSIX.

Les horloges et les minuteries POSIX sont des mécanismes qui permettent de gérer les événements temporisés et les alarmes dans le système.

<br />

#### 7. Enable support for printk
Permet d'activer la prise en charge de printk, qui est une fonction de débogage qui permet d'afficher des messages de débogage dans le noyau.

<br />

#### 8. BUG() support
Permet de prendre en charge la fonction BUG(), qui est une fonction de débogage qui permet de détecter les erreurs dans le noyau.

<br />

#### 9. Enable ELF core dumps
Permet d'activer la prise en charge des dumps de noyau ELF, qui sont des fichiers qui contiennent les informations de débogage du noyau en cas d'erreur.

<br />

#### 10. Enable PC-Speaker support
Permet d'activer la prise en charge du haut-parleur PC, qui est un périphérique qui permet de produire des sons.

<br />

#### 11. Enable smaller-sized data structures for core (NEW)
Permet d'activer la prise en charge des structures de données de taille réduite pour le noyau, ce qui peut améliorer les performances du système.

<br />

#### 12. Enable futex support
Permet de prendre en charge les futex, qui sont des mécanismes de synchronisation rapide qui permettent de gérer les accès concurrents aux ressources système.

<br />

#### 13. Enable eventpoll support
Permet de prendre en charge les eventpoll, qui sont des mécanismes de notification d'événements qui permettent de gérer les événements système.

<br />

#### 14. Enable signalfd() system call
Permet permet de prendre en charge l'appel système signalfd(), qui permet de gérer les signaux système.

<br />

#### 15. Enable timerfd() system call
Permet permet de prendre en charge l'appel système timerfd(), qui permet de gérer les minuteries système.

<br />

#### 16. Enable eventfd() system call
Permet de prendre en charge l'appel système eventfd(), qui permet de gérer les événements système.

<br />

#### 17. Use full shmem filesystem
Permet d'utiliser le système de fichiers shmem complet, qui est un système de fichiers virtuel qui fournit des informations sur les ressources système.

<br />

#### 18. Enable AIO support
Permet en charge les entrées-sorties asynchrones (AIO), qui permettent de gérer les opérations d'entrée-sortie de manière asynchrone.

<br />


#### 19. Enable IO uring support
Active la prise en charge d'IO uring, qui est une interface d'E/S haute performance qui permet des opérations d'E/S efficaces et scalables.

<br />

#### 20. Enable madvise/fadvise syscalls
Active la prise en charge des appels système madvise et fadvise, qui permettent aux applications de conseiller le noyau sur leur utilisation de la mémoire et leurs modèles d'accès.

<br />

#### 21. Enable membarrier() system call
Active la prise en charge de l'appel système membarrier, qui permet aux applications de synchroniser l'accès à la mémoire entre plusieurs threads et processus.

<br />

#### 22. Enable kcmp() system call
Active la prise en charge de l'appel système kcmp, qui permet aux applications de comparer l'état de deux processus.

<br />

#### 23. Enable rseq() system call
Active la prise en charge de l'appel système rseq, qui permet aux applications d'exécuter des séquences de appels système redémarrables.
<br />

#### 24. Enable debugging of rseq() system call
Active la prise en charge du débogage de l'appel système rseq, qui permet aux développeurs de déboguer et de tester l'appel système rseq.

<br />

#### 25. Enable cachestat() system call (NEW)
Active la prise en charge de l'appel système cachestat, qui permet aux applications de récupérer des statistiques de cache et des métriques de performance.

<br />

#### 26. PC/104 support
Active la prise en charge du bus PC/104, qui est un bus compact et robuste utilisé dans les systèmes embarqués.

<br />

#### 27. Load all symbols for debugging/ksymoops
Charge tous les symboles du noyau pour le débogage et ksymoops, ce qui permet aux développeurs de déboguer et d'analyser les erreurs et les crashes du noyau.

<br />

#### 28. Test the basic functions and performance of kallsyms (NEW)
Teste les fonctions de base et les performances de kallsyms, qui est un module du noyau qui fournit des informations de symboles pour le débogage et l'analyse du noyau.

<br />

#### 29. Include all symbols in kallsyms
Inclut tous les symboles du noyau dans kallsyms, ce qui permet aux développeurs d'accéder et d'analyser tous les symboles du noyau pour le débogage et l'analyse. 
