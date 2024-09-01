---------------------------------------------------------------------------------
# <p align='center'> Control Group Support </p>
---------------------------------------------------------------------------------
### A. Présentation
Ces options de compilation permettent de gérer les ressources système et de contrôler les performances du système en fonction des besoins des tâches et des groupes de tâches.

Elles peuvent aider à améliorer les performances globales du système, à réduire la consommation d'énergie et à éviter les problèmes de surcharge et de sous-utilisation des ressources.

J'espère que cela vous a aidé à comprendre ces options de compilation. Si vous avez des questions supplémentaires, n'hésitez pas à me demander.


<br />

### B. Configuration
#### 01. Favor dynamic modification latency reduction by default
Permet de réduire la latence de modification dynamique des paramètres de gestion de ressources. Lorsque cette option est activée, le système d'exploitation donne la priorité à la réduction de la latence de modification des paramètres de gestion de ressources, ce qui peut améliorer les performances globales du système.

<br />

#### 02. Memory controller
Permet d'activer le contrôleur de mémoire, qui permet de gérer la quantité de mémoire allouée à chaque groupe de tâches. Le contrôleur de mémoire peut aider à éviter les problèmes de surcharge de mémoire et à améliorer les performances globales du système.

<br />

#### 03. IO controller
Permet d'activer le contrôleur d'E/S, qui permet de gérer les opérations d'E/S (entrée/sortie) pour chaque groupe de tâches. Le contrôleur d'E/S peut aider à éviter les problèmes de surcharge d'E/S et à améliorer les performances globales du système.

<br />

#### 04. Utilization clamping per group of tasks
Permet d'activer le clamping d'utilisation pour chaque groupe de tâches. Le clamping d'utilisation permet de limiter l'utilisation des ressources par les tâches pour éviter les problèmes de surcharge et de sous-utilisation.
<br />

#### 05. PIDs controller
Permet d'activer le contrôleur de PIDs (Process ID), qui permet de gérer le nombre de processus créés par chaque groupe de tâches. Le contrôleur de PIDs peut aider à éviter les problèmes de surcharge de processus et à améliorer les performances globales du système.

<br />

#### 06. RDMA controller
Permet d'activer le contrôleur de RDMA (Remote Direct Memory Access), qui permet de gérer les opérations de RDMA pour chaque groupe de tâches. Le contrôleur de RDMA peut aider à éviter les problèmes de surcharge de RDMA et à améliorer les performances globales du système.

<br />

#### 07. Freezer controller
Permet d'activer le contrôleur de freezer, qui permet de geler les processus pour chaque groupe de tâches. Le contrôleur de freezer peut aider à éviter les problèmes de surcharge de processus et à améliorer les performances globales du système.

<br />

#### 08. HugeTLB controller
Permet  d'activer le contrôleur de HugeTLB (Huge Translation Lookaside Buffer), qui permet de gérer les pages de mémoire de grande taille pour chaque groupe de tâches. Le contrôleur de HugeTLB peut aider à améliorer les performances globales du système.

<br />

#### 09. Cpuset controller
Permet d'activer le contrôleur de cpuset, qui permet de gérer les ressources de processeur pour chaque groupe de tâches. Le contrôleur de cpuset peut aider à éviter les problèmes de surcharge de processeur et à améliorer les performances globales du système.

<br />

#### 10. Include legacy /proc/<pid>/cpuset file
Permet d'inclure le fichier /proc//cpuset pour assurer la compatibilité avec les anciennes versions du système d'exploitation.

<br />

#### 11. Device controller
Permet d'activer le contrôleur de périphérique, qui permet de gérer les périphériques pour chaque groupe de tâches. Le contrôleur de périphérique peut aider à éviter les problèmes de surcharge de périphérique et à améliorer les performances globales du système.

<br />

#### 12. Simple CPU accounting controller
Permet d'activer le contrôleur de comptabilité de processeur simple, qui permet de gérer les ressources de processeur pour chaque groupe de tâches. Le contrôleur de comptabilité de processeur simple peut aider à améliorer les performances globales du système.

<br />

#### 13. Perf controller
Permet d'activer le contrôleur de performances, qui permet de gérer les performances pour chaque groupe de tâches. Le contrôleur de performances peut aider à améliorer les performances globales du système.

<br />

#### 14. Support for eBPF programs attached to cgroups
Permet de prendre en charge les programmes eBPF (extended Berkeley Packet Filter) attachés aux groupes de contrôle. Les programmes

<br />

#### 15. Misc resource controller
Permet d'activer le contrôleur de ressources diverses, qui permet de gérer les ressources système telles que les sockets, les ports, les fichiers, etc. pour chaque groupe de tâches. Le contrôleur de ressources diverses peut aider à éviter les problèmes de surcharge de ressources système et à améliorer les performances globales du système.

<br />

#### 16. Debug controller
Permett d'activer le contrôleur de débogage, qui permet de gérer les ressources de débogage pour chaque groupe de tâches. Le contrôleur de débogage peut aider à identifier et à résoudre les problèmes de performances et de stabilité du système.



<br />




