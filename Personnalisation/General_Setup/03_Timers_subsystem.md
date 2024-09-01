----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# <p align='center'> Timers Sub-System </p>
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### A. Présentation
Ces options de compilation du kernel permettent de configurer les paramètres de temporisation, de sécurité et de précision du noyau Linux.

Il est important de choisir les options qui conviennent le mieux à vos besoins spécifiques.

<br />

### B. Configuration

#### 1. Timer tick handling [A Définir] (Amélioration perf / Risque de stress PC)
L'option de gestion des ticks de temporisateur (CONFIG_HZ) définit la fréquence à laquelle le noyau Linux met à jour les compteurs de temps et exécute les tâches périodiques.

Une fréquence plus élevée peut améliorer la précision des compteurs de temps, mais peut également augmenter la charge du processeur.

Les valeurs possibles sont :
- 100 Hz  : le noyau met à jour les compteurs de temps 100  fois par seconde. (par défaut)
- 250 Hz  : le noyau met à jour les compteurs de temps 250  fois par seconde.
- 300 Hz  : le noyau met à jour les compteurs de temps 300  fois par seconde.
- 1000 Hz : le noyau met à jour les compteurs de temps 1000 fois par seconde.

<br />

#### 2. Force user context tracking []
Permet au noyau de suivre le contexte utilisateur, ce qui signifie que le noyau peut identifier les processus qui sont en cours d'exécution en mode utilisateur.

Cette option est utile pour les applications qui nécessitent une sécurité accrue, comme les applications de virtualisation.

<br />

#### 3. Old Idle dynticks config []
Permet au noyau de désactiver les ticks de temporisateur lorsque le système est inactif, ce qui peut réduire la consommation d'énergie.

Il existe deux options :
- CONFIG_NO_HZ=y       : Le noyau désactive les ticks de temporisateur lorsque le système est inactif.
- CONFIG_NO_HZ_FULL=y  : Le noyau désactive complètement les ticks de temporisateur, même lorsque le système est actif.
<br />


#### 4. High Resolution Timer Support []
Permet au noyau de prendre en charge les temporisateurs haute résolution, qui peuvent fournir une précision plus élevée que les temporisateurs standards.

Cette option est utile pour les applications qui nécessitent une précision temporelle élevée, comme les applications de mesure de temps.

<br />

#### 5. ClockSource Watchdog maximum allowable skew (in ms)
Définit la valeur maximale de dérive autorisée pour le watchdog de la source d'horloge. Le watchdog de la source d'horloge est un mécanisme qui vérifie si la source d'horloge est stable et précise.

Si la dérive dépasse la valeur maximale autorisée, le noyau peut prendre des mesures correctives pour garantir la stabilité du système.


☐ ☑
