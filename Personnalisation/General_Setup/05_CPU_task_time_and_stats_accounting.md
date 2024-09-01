---------------------------------------------------------------------------------
# <p align='center'>  CPU / Task time and stats accounting </p>
---------------------------------------------------------------------------------
### A. Présentation
Ces options permettent de configurer la façon dont les statistiques et les informations sur les processus sont collectées et exportées dans le kernel.

Il est important de bien comprendre les implications de chaque option avant de les activer ou de les désactiver.

<br />
<br />

### B. Configuraition
#### 1. Cputime accounting []
Permet d'activer la comptabilité du temps CPU, qui permet de mesurer le temps passé par chaque processus en mode utilisateur et en mode noyau.

Cela permet de fournir des informations précises sur l'utilisation du CPU par les processus.
<br />

#### 2. Fine granularity task level IRQ time accounting []
Permet d'activer la comptabilité du temps d'interruption IRQ de niveau tâche avec une granularité fine.

Cela permet de mesurer le temps passé par chaque processus en traitement des interruptions IRQ, ce qui peut aider à identifier les processus qui consomment le plus de temps CPU.

<br />

#### 3. BSD Process Accounting []
Permet d'activer la comptabilité des processus BSD, qui permet de collecter des informations sur les processus qui se terminent, telles que le temps CPU utilisé, la mémoire utilisée, etc.

Cela peut aider à identifier les processus qui consomment le plus de ressources système.

<br />

#### 4. Export task/process statistics through netlink []
Permet d'activer l'exportation des statistiques des tâches/processus via netlink, qui permet de collecter et de transmettre des informations sur les processus en cours d'exécution, telles que le temps CPU utilisé, la mémoire utilisée, etc.

Cela peut aider à surveiller les processus en temps réel.

<br />

#### 5. Pressure stall information tracking []
Permet d'activer le suivi des informations de blocage de pression, qui permet de collecter des informations sur les processus qui sont bloqués en raison d'une pression sur les ressources système, telles que la mémoire ou le CPU.

Cela peut aider à identifier les processus qui sont affectés par la pression sur les ressources système.
<br />

☐
☑
