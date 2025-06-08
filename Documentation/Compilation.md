--------------------------------------------------------------------------------------
# <p align='center'> Compilation du Noyau 6.10.7 (Release: Juillet 2024) </p>

--------------------------------------------------------------------------------------
## I. Construction du Noyau
Il est nécessaire d'avoir 25 Go d'espace libre.

### A. Preparation Environnement du Noyau 6.10.7
``` bash
clear;
BRANCHE="6"
VERSION="$BRANCHE.10.7"
rm -r linux-${VERSION}* 2>/dev/null
wget https://cdn.kernel.org/pub/linux/kernel/v${BRANCHE}.x/linux-${VERSION}.tar.xz 2>/dev/null;
tar -xf linux-${VERSION}.tar.xz;
cd linux-${VERSION};
```

### C. Patch
```bash
clear;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.7.xz
unxz patch-6.10.7.xz
cd linux-6.10.7
patch -p1 < ../patch-6.10.7
```

<br />

### B. Menu de configuration
Touche Z permet d'afficher le menu caché
```bash
clear;
head Makefile -n 4;
make menuconfig;
```

<br />

### C. Compilation en Multi-Core
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

### D. Installer les modules
```bash
make modules_install;
```

<br />

### E. Déployer le Noyau
```bash
clear;
SOURCE="/Data/linux-*/arch/x86_64/boot"
KERNEL_NAME="vmlinuz-marc"
cp $SOURCE/bzImage /boot/$KERNEL_NAME;
```

### E. Mettre à jour grub
```bash
clear;
update-grub;
```
