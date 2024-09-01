---------------------------------------------------------------------------------
# <p align='center'> Kernel Performance Events And Counters </p>
---------------------------------------------------------------------------------
### A. Présentation
En général, cette option est destinée à des fins de débogage et ne doit pas être utilisée en production.

Cependant, il est important de noter que l'utilisation de vmalloc() peut avoir un impact sur les performances, car elle est plus lente et consomme plus de mémoire que l'allocation de mémoire de la page du noyau.

<br />

### B. Configuration
#### 1. Kernel performance events and counters Debug: use vmalloc to back perf mmap() buffers
Cette option de compilation du noyau (kernel) active un comportement de débogage pour les événements et compteurs de performance.

Le noyau Linux utilise la fonction perf_mmap() pour allouer la mémoire pour les buffers de performance. Ces buffers stockent des informations sur les événements de performance, comme le nombre de cycles d'horloge utilisés par un processus ou le nombre de cache misses.

Par défaut, perf_mmap() utilise le système d'allocation de mémoire de la page du noyau. Cela signifie que la mémoire est allouée à partir d'un pool de pages spécifiques au noyau, et elle est gérée par le noyau.

L'option Debug: use vmalloc to back perf mmap() buffers active un mode de débogage dans lequel perf_mmap() utilise la fonction vmalloc() au lieu de l'allocation de mémoire de la page du noyau. La fonction vmalloc() est une fonction d'allocation de mémoire plus flexible qui permet de réserver de grands blocs de mémoire contiguës.


**Activer ce mode de débogage peut être utile pour :**
```
Détecter les erreurs d'allocation de mémoire:
- En utilisant vmalloc(), vous pouvez détecter plus facilement les erreurs d'allocation de mémoire qui pourraient se produire dans le code du noyau lié à la gestion des buffers de performance.

Simplifier le débogage:
- En utilisant vmalloc(), les buffers de performance sont alloués dans l'espace d'adressage utilisateur, ce qui peut faciliter le débogage des buffers à l'aide d'outils comme gdb.


Obtenir des informations plus détaillées:
- En utilisant vmalloc(), vous pouvez obtenir des informations plus détaillées sur l'allocation et l'utilisation de la mémoire des buffers de performance.
```

