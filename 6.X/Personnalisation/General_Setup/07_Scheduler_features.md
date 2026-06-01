---------------------------------------------------------------------------------
# <p align='center'> Scheduler features </p>
---------------------------------------------------------------------------------
## A. Présentation
L'option de compilation "Enable utilization clamping for RT/FAIR tasks" permet d'activer le clamping d'utilisation pour les tâches RT et FAIR.

Cette technique permet de limiter l'utilisation des ressources par les tâches pour éviter les problèmes de surcharge et de sous-utilisation, et améliorer les performances globales du système.

Elle est particulièrement utile pour les systèmes qui exécutent des tâches critiques en temps réel.

J'espère que cela vous a aidé à comprendre cette option de compilation. Si vous avez des questions supplémentaires, n'hésitez pas à me demander.

<br />

## B. Configuration
### 1. Enable utilization clamping for RT/FAIR tasks []
Permet d'activer le clamping d'utilisation pour les tâches RT (Real-Time) et FAIR (Fair Scheduling).

Le clamping d'utilisation est une technique qui permet de limiter l'utilisation des ressources par les tâches pour éviter les problèmes de surcharge et de sous-utilisation.

Lorsque cette option est activée, le système d'exploitation peut ajuster la fréquence d'horloge et la quantité de ressources allouées aux tâches RT et FAIR en fonction de leurs besoins réels.

Cela permet de réduire la consommation d'énergie et de améliorer les performances globales du système.

Le clamping d'utilisation est particulièrement utile pour les systèmes qui exécutent des tâches critiques en temps réel, telles que les systèmes de contrôle de processus, les systèmes de navigation et les systèmes de communication.

Il permet de garantir que les tâches critiques reçoivent les ressources nécessaires pour fonctionner correctement, tout en évitant les problèmes de surcharge et de sous-utilisation.

<br />

### 2. Number of supported utilization clamp buckets
