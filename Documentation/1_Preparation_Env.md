-------------------------------------------------------------------------------------------------------
# <p align='center'> Préparation de l'environnement pour la compilation </p>

-------------------------------------------------------------------------------------------------------
## I. Installation des dépendances
Pour Debian 12 (Bookworm), voici la liste de paquets mise à jour pour compiler le noyau Linux :

### A. Paquets de base
- **build-essential** : fournit les outils de base pour la compilation, tels que gcc, make, etc.
- **libncurses6-dev** : fournit les bibliothèques de développement pour les interfaces utilisateur en mode texte
- **libssl-dev**      : fournit les bibliothèques de développement pour les fonctionnalités de sécurité SSL/TLS
- **libelf-dev**      : fournit les bibliothèques de développement pour les fichiers ELF (Executable and Linkable Format)

```bash
apt install build-essential libncurses6-dev libssl-dev libelf-dev;
```

<br />

### B. Paquets pour la compilation du noyau
- **linux-headers-W.X.X-Z-amd64** : fournit les en-têtes de noyau pour la version actuelle du noyau
- **linux-source-W.X.X-Z-amd64**  : fournit le code source du noyau pour la version actuelle du noyau
- **libgcc-X.X-dev**              : fournit les bibliothèques de développement pour la version actuelle de GCC

<br />

### C. Paquets pour les dépendances du noyau
- **libpci-dev**       : fournit les bibliothèques de développement pour les périphériques PCI
- **libusb-dev**       : fournit les bibliothèques de développement pour les périphériques USB
- **libieee1275-dev**  : fournit les bibliothèques de développement pour les périphériques IEEE 1275 (Open Firmware)
- **libdevmapper-dev** : fournit les bibliothèques de développement pour les gestionnaires de disques logiques (LVM, etc.)

```bash
apt install libpci-dev libusb-dev libieee1275-dev libdevmapper-dev;
```

<br />

### D. Paquets pour les outils de développement
- **git**         : fournit le système de gestion de version Git
- **fakeroot**    : fournit un environnement de compilation avec des droits d'accès élevés
- **ncurses-dev** : fournit les bibliothèques de développement pour les interfaces utilisateur en mode texte
- **libqt4-dev**  : fournit les fichiers d'en-tête et les bibliothèques statiques nécessaires pour compiler des applications qui utilisent la bibliothèque Qt 4. (Paquet retiré)
- **qtbase5-dev** : Remplace le paquet libqt4-dev

```bash
apt install git fakeroot ncurses-dev libqt4-dev qtbase5-dev;
```
<br />

### E. Paquets pour les dépendances spécifiques
- **libcrypto-dev** : fournit les bibliothèques de développement pour les fonctionnalités de cryptographie
- **libz-dev**      : fournit les bibliothèques de développement pour la compression de données
- **liblz4-dev**    : fournit les bibliothèques de développement pour la compression de données LZ4
- **liblzma-dev**   : fournit les bibliothèques de développement pour la compression de données LZMA
- **libbpf-dev**    : fournit les bibliothèques de développement pour les programmes de filtrage de paquets (BPF)

```bash
apt install libcrypto-dev libz-dev liblz4-dev liblzma-dev libbpf-dev;
```

<br />
