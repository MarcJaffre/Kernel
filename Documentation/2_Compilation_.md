--------------------------------------------------------------------------------------
# <p align='center'> Compilation du Noyau 6.10.X (Release: Juillet 2024) </p>

--------------------------------------------------------------------------------------
## I. Construction du Noyau 
Il est nécessaire d'avoir 25 Go d'espace libre. ()

### A. Selection du Noyau ( [6.10.0](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tag/?h=v6.10) )
``` bash
##############################################################################################################################
# Dossier de Travail #
######################
clear;
cd $HOME; rm -r kernel 2>/dev/null; mkdir kernel; cd kernel;

##############################################################################################################################
# Telechargements #
###################
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.10.tar.xz  2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.1.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.2.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.3.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.4.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.5.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.6.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.7.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.8.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.9.xz    2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.10.xz   2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.11.xz   2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.12.xz   2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.13.xz   2>/dev/null;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.10.14.xz   2>/dev/null;

##############################################################################################################################
# Decompression #
#################
for i in $(ls *.xz); do unxz   $i 2>/dev/null; done;
for i in $(ls *.tar);do tar xf $i 2>/dev/null; done;
cd /root/kernel/linux-6.10;

##############################################################################################################################
# Patch 6.10.1 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.1 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 1/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.2 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.2 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 2/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.3 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.3 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 3/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.4 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.4 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 4/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.5 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.5 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 5/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.6 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.6 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 6/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.7 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.7 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 7/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.8 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.8 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 8/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.9 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.9 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 9/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.10 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.10 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 10/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.11 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.11 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 11/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.12 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.12 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 12/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.13 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.13 1>/dev/null; make kernelversion;
sed -i -e "s/SUBLEVEL \= 13/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.14 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.14 1>/dev/null;
sleep 5;

##############################################################################################################################
# Verification de la version #
##############################
clear;
head Makefile -n 4 | grep -v "SPDX";
```

```
VERSION = 6
PATCHLEVEL = 10
SUBLEVEL = 14
```

<br />

### B. Récupérer sa configuration du Noyau
La commande suivante permet de récupérer la configuration de son noyau
```bash
#############################################################################################################
clear;
cp /boot/config-$(uname -r) .config;
#############################################################################################################
```

<br />

### F. Mise à jour de la configuration
La commande suivant permet de mettre à jour la configuration. (Si nouvelle option, question)
```bash
#############################################################################################################
clear;
yes "" | make oldconfig 1>/dev/null;
#############################################################################################################
```

<br />

### X. Menu de configuration
Touche Z permet d'afficher le menu caché.
```bash
#############################################################################################################
clear;
make menuconfig;
#############################################################################################################
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
#############################################################################################################
clear;
make -j$(nproc) ARCH=$(arch);
#make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1;
#############################################################################################################
```

#### 2. CheckPoint
Permet la reprise de la compilation
```bash
#############################################################################################################
clear;
make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1 checkpoint;
make -j$(nproc) -O3 -march=native -mtune=native > build.log 2>&1 checkpoint-restore;
#############################################################################################################
``` 

<br />

### X. Installer les modules
```bash
#############################################################################################################
clear;
make modules_install;
#############################################################################################################
```

<br />

### X. Déployer le Noyau
```bash
#############################################################################################################
clear;
SOURCE="/Data/linux-*/arch/x86_64/boot"
KERNEL_NAME="vmlinuz-marc"
cp $SOURCE/bzImage /boot/$KERNEL_NAME;
#############################################################################################################
```

### X. Mettre à jour grub
```bash
#############################################################################################################
clear;
update-grub;
#############################################################################################################
```


