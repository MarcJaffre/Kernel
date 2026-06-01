---------------------------------------------------------------------------------
# <p align='center'> Kexec and crash features </p>
---------------------------------------------------------------------------------
## A. Présentation

<br />

## B. Configuration
### 1. Enable kexec system call []
Permet d'utiliser la commande `kexec` pour redémarrer le système avec un nouveau noyau sans avoir à redémarrer complètement le système.

<br />

### 2. Enable kexec file based system call []
Permet de charger un nouveau noyau à partir d'un fichier sur le système de fichiers.

<br />

### 3. Verify kernel signature during kexec_file_load() syscall []
Permet de s'assurer que le noyau que vous chargez est authentique et n'a pas été modifié.

#### A. Require a valid signature in kexec_file_load() syscall []
Permet de s'assurer que le noyau que vous chargez est signé par une autorité de confiance.

#### B. Enable Image signature verification support (ARM) []
Permet de vérifier la signature d'un fichier image ARM, afin de s'assurer qu'il n'a pas été modifié.

#### C. Enable bzlmage signature verification support []
Permet de vérifier la signature d'un fichier bzlmage, afin de s'assurer qu'il n'a pas été modifié.

<br />

### 4. kexec jump []
Permet d'utiliser `kexec` pour sauter sur un autre noyau sans redémarrer le système.

<br />

### 5. kernel crash dumps []
Permet d'enregistrer les informations sur les plantages du noyau, ce qui peut aider à déboguer les problèmes.

#### A. Update the crash elfcorehdr on system configuration changes (NEW) []
Permet de mettre à jour les informations sur le plantage du noyau lorsque la configuration du système chang

#### B. Specify the maximum number of memory regions for the elfcorehdr (NEW) []
Permet de spécifier le nombre maximum de régions de mémoire qui peuvent être utilisées pour stocker les informations sur le plantage du noyau.
