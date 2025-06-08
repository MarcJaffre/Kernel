--------------------------------------------------------------------------------------
# <p align='center'> Compilation du Noyau 6.10.7 (Release: Juillet 2024) </p>

--------------------------------------------------------------------------------------
## I. Construction du Noyau
Il est nécessaire d'avoir 25 Go d'espace libre.

### A. Selection du Noyau (6.10.1)
``` bash
clear;
#############################################################################################################
KERNEL_SITE="https://cdn.kernel.org/pub/linux/kernel"
KERNEL_VERSION="6"
KERNEL_PATCHLEVEL="10"
KERNEL_SUBLEVEL="1"
KERNEL_RELEASE="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.${KERNEL_SUBLEVEL}"

PATCH_2="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.2"
PATCH_3="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.3"
PATCH_4="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.4"
PATCH_5="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.5"
PATCH_6="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.6"
PATCH_7="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.7"
PATCH_8="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.8"
PATCH_9="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.9"
PATCH_10="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.10"
PATCH_11="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.11"
PATCH_12="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.12"
PATCH_13="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.13"
PATCH_14="${KERNEL_VERSION}.${KERNEL_PATCHLEVEL}.14"
#############################################################################################################
```

<br />

### B. Téléchargement du Noyaux
```bash
clear;
cd $HOME;
rm -r linux-${VERSION}* 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/linux-${KERNEL_RELEASE}.tar.xz 2>/dev/null;
tar -xf linux-${KERNEL_RELEASE}.tar.xz;
cd linux-${KERNEL_RELEASE};
```

<br />

### C. Vérifier Release
```bash
head Makefile -n 4;
```

```
VERSION = 6
PATCHLEVEL = 10
SUBLEVEL = 1
```

<br />


### D. Patchs
Il faut partir de la partie Release 6.10.X du noyau. (6.10.1)
#### 1. Telechargement
```bash
clear;
rm patch-* 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_2}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_3}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_4}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_5}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_6}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_7}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_8}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_9}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_10}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_11}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_12}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_13}.xz 2>/dev/null;
wget $KERNEL_SITE/v${KERNEL_VERSION}.x/patch-${PATCH_14}.xz 2>/dev/null;
for i in $(ls *.xz); do unxz $i; done
ls patch-* | wc -l
```
#### 2. Application
```bash
clear;
patch -p1 --batch < ./patch-${PATCH_1} 2>/dev/null;
patch -p1 --batch < ./patch-${PATCH_2} 2>/dev/null;
patch -p1 --batch < ./patch-${PATCH_3} 2>/dev/null;
patch -p1 --batch < ./patch-${PATCH_4} 2>/dev/null;
patch -p1 --batch < ./patch-${PATCH_5} 2>/dev/null;
patch -p1 --batch < ./patch-${PATCH_6} 2>/dev/null;
patch -p1 --batch < ./patch-${PATCH_7} 2>/dev/null;
grep "SUBLEVEL =" Makefile;
```




<br />

### E. Récupérer sa configuration du Noyau
La commande suivante permet de récupérer la configuration de son noyau
```bash
clear;
cp /boot/config-$(uname -r) .config;
```

<br />

### F. Mise à jour de la configuration
La commande suivant permet de mettre à jour la configuration. (Si nouvelle option, question)
```bash
clear;
yes "" | make oldconfig ARCH=$(arch)
```

<br />

### X. Menu de configuration
Touche Z permet d'afficher le menu caché.
```bash
clear;
make menuconfig;
```

<br />

### X. Compilation en Multi-Core
#### 1. Sans CheckPoint
Si on souhaite `X` Core, il suffit de remplacer `$(nproc)` par le nombre de core qui compilerons.
```
-O3 pour activer l'optimisation du code en utilisant le cache L2 et L3. 
-O2 pour activer l'optimisation du code
-march=native pour compiler pour l'architecture native du processeur
-mtune=native pour ajuster les paramètres de compilation pour l'architecture native du processeur
```

```bash
clear;
make -j$(nproc) ARCH=$(arch);
#make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1;
```

#### 2. CheckPoint
Permet la reprise de la compilation
```bash
clear;
make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1 checkpoint;
make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1 checkpoint-restore;
``` 

<br />

### X. Installer les modules
```bash
make modules_install;
```

<br />

### X. Déployer le Noyau
```bash
clear;
SOURCE="/Data/linux-*/arch/x86_64/boot"
KERNEL_NAME="vmlinuz-marc"
cp $SOURCE/bzImage /boot/$KERNEL_NAME;
```

### X. Mettre à jour grub
```bash
clear;
update-grub;
```


