---------------------------------------------------------------------------------
# <p align='center'> RCU Subsystem </p>
---------------------------------------------------------------------------------
## A. Présentation
Les options de compilation liées à RCU permettent de configurer et d'optimiser les performances de RCU.

Les options incluent la sélection de l'implémentation de RCU, la définition des valeurs de fanout, l'activation du renforcement de priorité, la décharge du traitement des rappels et l'utilisation de barrières de mémoire.

Les nouvelles fonctionnalités incluent l'invocation paresseuse des rappels et la vérification de la durée de sauvegarde des rappels.

J'espère que cela vous a aidé à comprendre les options de compilation liées à RCU. Si vous avez des questions supplémentaires, n'hésitez pas à me demander.


<br />

## B. Configuration
### 1. Make expert-level adjustments to RCU
Permet d'activer les ajustements de niveau expert pour RCU, qui permettent de configurer les paramètres internes de RCU pour optimiser les performances.

<br />

### 2. Configuration Force selection of TASKS_RCU
Permet de sélectionner TASKS_RCU comme implémentation de RCU pour les tâches. Cela permet de gérer les mises à jour des données partagées entre les tâches de manière efficace.

<br />

### 3. Force selection of Tasks Rude RCU
Permet de sélectionner Tasks Rude RCU comme implémentation de RCU pour les tâches. Cela permet de gérer les mises à jour des données partagées entre les tâches de manière efficace, mais avec une approche plus agressive.

<br />

### 4. Force selection of Tasks Trace RCU
Permet de sélectionner Tasks Trace RCU comme implémentation de RCU pour les tâches. Cela permet de gérer les mises à jour des données partagées entre les tâches de manière efficace, tout en fournissant des informations de traçage pour le débogage.

#### A. Tree-based hierarchical RCU fanout value
Permet de configurer la valeur de fanout hiérarchique de RCU basée sur les arbres. Cela permet de contrôler la manière dont les mises à jour des données partagées sont propagées dans l'arbre de RCU.

#### B. Tree-based hierarchical RCU leaf-level fanout value
Permet de configurer la valeur de fanout de niveau feuille de RCU basée sur les arbres. Cela permet de contrôler la manière dont les mises à jour des données partagées sont propagées dans les feuilles de l'arbre de RCU.

<br />

### 5. Enable RCU priority boosting
Permet d'activer le renforcement de priorité de RCU, qui permet de donner la priorité aux tâches qui ont besoin d'accéder aux données partagées.

<br />

### 6. Offload RCU callback processing from boot-selected CPUs
Permet de décharger le traitement des rappels de RCU des CPU sélectionnées au démarrage. Cela permet de réduire la charge de travail sur les CPU sélectionnées.

<br />

### 7. Tasks Trace RCU readers use memory barriers in user and idle
Permet de configurer les lecteurs de Tasks Trace RCU pour qu'ils utilisent des barrières de mémoire en mode utilisateur et inactif. Cela permet de garantir la cohérence des données partagées.

<br />

### 8. RCU callback lazy invocation functionality (NEW)
Permet d'activer la fonctionnalité d'invocation lazy des rappels de RCU, qui permet de retarder l'exécution des rappels de RCU jusqu'à ce que les données partagées soient réellement nécessaires.

<br />

### 9. RCU callback-batch backup time check
Permet de configurer la vérification de la sauvegarde du traitement par lots des rappels de RCU. Cela permet de garantir que les rappels de RCU sont traités de manière efficace et en temps opportun.

<br />

☐ ☑
