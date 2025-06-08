--------------------------------------------------------------------------------------
# <p align='center'> Compilation du Noyau 6.10.X (Release: Juillet 2024) </p>

--------------------------------------------------------------------------------------
## I. Construction du Noyau 
Il est nécessaire d'avoir 25 Go d'espace libre. ()

### A. Selection du Noyau ( [6.10.0](https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/tag/?h=v6.10) )
``` bash
##############################################################################################################################
# Nettoyage console #
#####################
clear;

##############################################################################################################################
# Variables d-environnement #
#############################
KERNEL_MAJOR="6"
KERNEL_MINOR="10"
URL="https://cdn.kernel.org/pub/linux/kernel/v${KERNEL_MAJOR}.x/"
URL_KERNEL="$URL/linux-${KERNEL_MAJOR}.${KERNEL_MINOR}.tar.xz"

##############################################################################################################################
# Dossier de Travail #
######################
cd $HOME;
rm -r kernel 2>/dev/null;
mkdir kernel 2>/dev/null;
cd kernel;

##############################################################################################################################
# Telechargement du Kernel #
############################
wget ${URL_KERNEL} 2>/dev/null;

##############################################################################################################################
# Telechargement des Patchs #
#############################
for i in $(curl -s "$URL" | grep -oP "patch-${KERNEL_MAJOR}\.${KERNEL_MINOR}\.\d+\.xz" | grep -v '\.xz\.1$'); do
  wget "${URL}${i}" 2>/dev/null;
done
#
##############################################################################################################################
# Decompression #
#################
# --------------------------------------------- #
for i in $(ls *.xz | grep -v '\.xz\.1$'); do
  unxz $i 2>/dev/null;
done;
# --------------------------------------------- #
for i in $(ls *.tar); do
  tar xf $i 2>/dev/null;
done;
# --------------------------------------------- #
for i in $(ls *.xz.1); do
  rm $i;
done;
# --------------------------------------------- #
cd linux-${KERNEL_MAJOR}.${KERNEL_MINOR};

##############################################################################################################################
# Patchage #
############
clear;
for i in $(ls ../patch-6.10.* | sort -V | xargs -n1 basename); do
  # --------------------------------------------------------
  echo "$i"
  patch -p1 --batch --ignore-whitespace < ../$i 1>/dev/null
  # --------------------------------------------------------
  PATCH=$(echo "$i" | cut -d "." -f 3)
  if [ -n "$PATCH" ]; then
    sed -i -e "s/SUBLEVEL = $PATCH/SUBLEVEL = 0/g" Makefile;
  fi
  # --------------------------------------------------------
  echo "La valeur SUBLEVEL est sur $(make kernelversion)";
  sleep 1;
  echo "";
  # --------------------------------------------------------
done


##############################################################################################################################
# Definir le SUBLEVEL sur le dernier patch #
# LAST_PATCH=$(ls ../patch-6.10.* | sort -V | xargs -n1 basename | tail -n 1 | cut -d "." -f 3)
# sed -i -e "s/SUBLEVEL = 0/SUBLEVEL = $LAST_PATCH/g" Makefile
##############################################################################################################################
```




```bash
##############################################################################################################################
# Message #
###########
echo "#################################";
echo "#       Patchage du Kernel      #";
echo "#################################";
echo "#                               #";
echo "# Kernel d'Originel : $(make kernelversion)    #";
echo "#                               #";
for i in $(ls patch*); do
echo $i
done

##############################################################################################################################
# Patch 6.10.1 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.1 1>/dev/null; 
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 1/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.2 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.2 1>/dev/null;
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 2/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.3 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.3 1>/dev/null;
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 3/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.4 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.4 1>/dev/null;
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 4/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.5 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.5 1>/dev/null;
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 5/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.6 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.6 1>/dev/null;
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 6/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.7 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.7 1>/dev/null;
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 7/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.8 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.8 1>/dev/null;
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 8/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.9 #
################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.9 1>/dev/null;
echo "# Patch : $(make kernelversion)                #";
sed -i -e "s/SUBLEVEL \= 9/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.10 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.10 1>/dev/null;
echo "# Patch : $(make kernelversion)               #";
sed -i -e "s/SUBLEVEL \= 10/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.11 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.11 1>/dev/null;
echo "# Patch : $(make kernelversion)               #";
sed -i -e "s/SUBLEVEL \= 11/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.12 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.12 1>/dev/null;
echo "# Patch : $(make kernelversion)               #";
sed -i -e "s/SUBLEVEL \= 12/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.13 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.13 1>/dev/null;
echo "# Patch : $(make kernelversion)               #";
sed -i -e "s/SUBLEVEL \= 13/SUBLEVEL \= 0/g" Makefile;

##############################################################################################################################
# Patch 6.10.14 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-6.10.14 1>/dev/null;
echo "#                               #";
echo "# Final : $(make kernelversion)               #";
echo "#                               #";
echo "#################################";
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
nano .config;
#############################################################################################################
```

```
CONFIG_BASE_SMALL=y
VFIO_VIRQFD=y
CONFIG_ANDROID_BINDER_IPC=n
CONFIG_FSCACHE_DEBUG=n
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
make clean;
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


