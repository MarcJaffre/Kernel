------------------------------------------------------------------------------------------------------------------------------------------
# <p align='center'> IRQ Sub-System </p>
------------------------------------------------------------------------------------------------------------------------------------------
### A. Présentation

<br />

### B. Configuraition
#### 1. Supportsparse irq numbering [Y]
Cette option active le support pour une numérotation d'interruption clairsemée. 

Dans un système avec une numérotation d'interruption clairsemée, les numéros d'interruption ne sont pas nécessairement continus.

Cela permet d'utiliser un plus petit nombre de numéros d'interruption tout en prenant en charge un grand nombre de périphériques.

<br />

#### 2. Expose irq internals in debugfs [Y] (Mitigé, Sécurité)
Cette option expose les informations internes sur les interruptions dans le système de fichiers debugfs.

Cela permet aux utilisateurs de déboguer les interruptions et de voir comment elles sont gérées par le noyau.


☐ ☑
