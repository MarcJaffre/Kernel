------------------------------------------------------------------------------------------------------------------------------------------
# <p align='center'> BPF Sub-System </p>
------------------------------------------------------------------------------------------------------------------------------------------
## A. Présentation
Ces options permettent de configurer la façon dont les programmes BPF sont exécutés et sécurisés dans le kernel.

Il est important de bien comprendre les implications de chaque option avant de les activer ou de les désactiver. 

<br />

## B. Configuration
### 1. Enable bpf() system call []
Permet d'activer l'appel système bpf() qui est utilisé pour charger et exécuter des programmes BPF.

Cela permet aux utilisateurs de créer des programmes BPF qui peuvent être exécutés dans le kernel.

<br />

### 2. Enable BPF Just In Time compiler []
Permet d'activer le compilateur BPF JIT qui compile les programmes BPF en code machine natif au moment de l'exécution.

Cela améliore les performances des programmes BPF.

<br />

### 3. Permanently enable BPF JIT and remove BPF interpreter []
Permet d'activer définitivement le compilateur BPF JIT et de supprimer l'interpréteur BPF.

Cela signifie que les programmes BPF seront toujours compilés en code machine natif et exécutés directement, sans passer par l'interpréteur.

<br />

### 4. Disable unprivileged BPF by default []
Permet de désactiver par défaut les programmes BPF non privilégiés. 

Cela signifie que seuls les utilisateurs privilégiés pourront charger et exécuter des programmes BPF.

<br />

### 5. Enable BPF LSM Instrumentation []
Permet d'activer l'instrumentation BPF LSM (Linux Security Module) qui fournit des hooks de sécurité pour les programmes BPF. Cela permet de contrôler l'accès aux ressources système et de renforcer la sécurité du système.

☐ ☑
