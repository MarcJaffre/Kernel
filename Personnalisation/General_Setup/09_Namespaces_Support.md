---------------------------------------------------------------------------------
# <p align='center'> Namespaces support </p>
---------------------------------------------------------------------------------
## A. Présentation
Ces options de compilation permettent de prendre en charge les différents espaces de nom qui définissent les paramètres système pour chaque processus ou groupe de processus.

Cela permet de créer des environnements système isolés pour chaque processus ou groupe de processus, ce qui peut améliorer la sécurité et la flexibilité du système.

<br />

## B. Configuration
### 1. UTS namespace []
Permet de prendre en charge les espaces de nom UTS (Unix Time-Sharing).

Un espace de nom UTS définit un ensemble de paramètres système tels que le nom d'hôte, le domaine, etc.

Chaque processus peut avoir son propre espace de nom UTS, ce qui signifie qu'il peut avoir son propre nom d'hôte, son propre domaine, etc.

L'avantage de l'utilisation des espaces de nom UTS est que cela permet de créer des environnements système isolés pour chaque processus ou groupe de processus, ce qui peut améliorer la sécurité et la flexibilité du système.

<br />

### 2. TIME namespace []
Permet de prendre en charge les espaces de nom TIME.

Un espace de nom TIME définit un ensemble de paramètres système tels que la date et l'heure système, le fuseau horaire, etc.

Chaque processus peut avoir son propre espace de nom TIME, ce qui signifie qu'il peut avoir sa propre date et heure système, son propre fuseau horaire, etc.

L'avantage de l'utilisation des espaces de nom TIME est que cela permet de créer des environnements système isolés pour chaque processus ou groupe de processus, ce qui peut améliorer la sécurité et la flexibilité du système.

<br />

### 3. IPC namespace []
Permet de prendre en charge les espaces de nom IPC (Inter-Process Communication).

Un espace de nom IPC définit un ensemble de paramètres système tels que les clés de messagerie, les sémaphores, les mémoires partagées, etc.

Chaque processus peut avoir son propre espace de nom IPC, ce qui signifie qu'il peut avoir ses propres clés de messagerie, ses propres sémaphores, ses propres mémoires partagées, etc.

L'avantage de l'utilisation des espaces de nom IPC est que cela permet de créer des environnements système isolés pour chaque processus ou groupe de processus, ce qui peut améliorer la sécurité et la flexibilité du système.

<br />

### 4. User namespace []
Permet de prendre en charge les espaces de nom utilisateur.
Un espace de nom utilisateur définit un ensemble de paramètres système tels que les identifiants d'utilisateur, les groupes d'utilisateur, etc.

Chaque processus peut avoir son propre espace de nom utilisateur, ce qui signifie qu'il peut avoir ses propres identifiants d'utilisateur, ses propres groupes d'utilisateur, etc.

L'avantage de l'utilisation des espaces de nom utilisateur est que cela permet de créer des environnements système isolés pour chaque processus ou groupe de processus, ce qui peut améliorer la sécurité et la flexibilité du système.

<br />

### 5. PID Namespaces []
Permet de prendre en charge les espaces de nom PID (Process ID).

Un espace de nom PID définit un ensemble de paramètres système tels que les identifiants de processus, les tables de processus, etc.

Chaque processus peut avoir son propre espace de nom PID, ce qui signifie qu'il peut avoir ses propres identifiants de processus, ses propres tables de processus, etc.

L'avantage de l'utilisation des espaces de nom PID est que cela permet de créer des environnements système isolés pour chaque processus ou groupe de processus, ce qui peut améliorer la sécurité et la flexibilité du système.

<br />

### 6. Network namespace []
Permet de prendre en charge les espaces de nom réseau.

Un espace de nom réseau définit un ensemble de paramètres système tels que les interfaces de réseau, les adresses IP, les routes, etc.

Chaque processus peut avoir son propre espace de nom réseau, ce qui signifie qu'il peut avoir ses propres interfaces de réseau, ses propres adresses IP, ses propres routes, etc.

L'avantage de l'utilisation des espaces de nom réseau est que cela permet de créer des environnements système isolés pour chaque processus ou groupe de processus, ce qui peut améliorer la sécurité et la flexibilité du système.
