--------------------------------------------------------------------------------------
# <p align='center'> Compilation du Noyau 6.10.7 (Release: Juillet 2024) </p>

--------------------------------------------------------------------------------------
## I. Construction du Noyau
Il est nécessaire d'avoir 25 Go d'espace libre.

### A. Selection du Noyau (6.10.7)
``` bash
clear;
KERNEL_VERSION="6"
KERNEL_PATCHLEVEL="10"
KERNEL_SUBLEVEL="7"
KERNEL_RELEASE="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.${KERNEL_SUBLEVEL}"
```

### B. Téléchargement du Noyaux
```bash
clear;
cd $HOME
rm -r linux-${VERSION}* 2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v${KERNEL_VERSION}.x/linux-${KERNEL_RELEASE}.tar.xz 2>/dev/null;
tar -xf linux-${KERNEL_RELEASE}.tar.xz;
cd linux-${KERNEL_RELEASE};
head Makefile -n 4;
```

### C. Générer la configuration
La commande suivante permet de récupérer la configuration de son noyau
```bash
clear;
cp /boot/config-$(uname -r) .config;
```


### D. Patch
```bash
clear;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-${KERNEL_RELEASE}.xz
unxz patch-${KERNEL_RELEASE}.xz
patch -p1 < ../patch-${KERNEL_RELEASE}
```

<br />

### E. Menu de configuration
Touche Z permet d'afficher le menu caché
```bash
clear;
make menuconfig;
```

<br />

### F. Compilation en Multi-Core
#### 1. Sans CheckPoint
Si on souhaite `X` Core, il suffit de remplacer `$(nproc)` par le nombre de core qui compilerons.
```
-O3 pour activer l'optimisation du code en utilisant le cache L2 et L3. 
-O2 pour activer l'optimisation du code
-march=native pour compiler pour l'architecture native du processeur
-mtune=native pour ajuster les paramètres de compilation pour l'architecture native du processeur
```

```bash
#make -j$(nproc) ARCH=$(arch);
make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1;
```

#### 2. CheckPoint
Permet la reprise de la compilation
```bash
clear;
make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1 checkpoint;
make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1 checkpoint-restore;
``` 

<br />

### G. Installer les modules
```bash
make modules_install;
```

<br />

### H. Déployer le Noyau
```bash
clear;
SOURCE="/Data/linux-*/arch/x86_64/boot"
KERNEL_NAME="vmlinuz-marc"
cp $SOURCE/bzImage /boot/$KERNEL_NAME;
```

### I. Mettre à jour grub
```bash
clear;
update-grub;
```
