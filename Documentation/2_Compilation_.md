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
for i in $(ls ../patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.* | sort -V | xargs -n1 basename); do
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
# LAST_PATCH=$(ls ../patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.* | sort -V | xargs -n1 basename | tail -n 1 | cut -d "." -f 3)
# sed -i -e "s/SUBLEVEL = 0/SUBLEVEL = $LAST_PATCH/g" Makefile
##############################################################################################################################
```

```bash
##############################################################################################################################
# Nettouage de la console #
###########################
clear;

##############################################################################################################################
# Telechargement #
##################
cd /Data;
rm -r kernel 2>/dev/null;
mkdir kernel;
cd kernel;
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
#
##############################################################################################################################
# Extraction #
##############
for i in $(ls *.xz); do unxz   $i 2>/dev/null; done;
for i in $(ls *.tar);do tar xf $i 2>/dev/null; done;
cd /Data/kernel/linux-{KERNEL_MAJOR}.{KERNEL_MINOR};
#
##############################################################################################################################
# Message #
###########
echo "#################################";
echo "#       Patchage du Kernel      #";
echo "#################################";
echo "#                               #";
echo "# Kernel d'Originel : $(make kernelversion)    #";
echo "#                               #";
echo "# Patch : $(make kernelversion)                #";
echo "#                               #";
echo "# Final : $(make kernelversion)               #";
echo "#                               #";
echo "#################################";
#
#
##############################################################################################################################
# Patch 6.10.1 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.1 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 1/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.2 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.2 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 2/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.3 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.3 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 3/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.4 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.4 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 4/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.5 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.5 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 5/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.6 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.6 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 6/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.7 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.7 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 7/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.8 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.8 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 8/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.9 #
################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.9 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 9/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.10 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.10 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 10/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.11 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.11 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 11/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.12 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.12 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 12/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.13 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.13 1>/dev/null; 
sed -i -e "s/SUBLEVEL \= 13/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.14 #
#################
patch -p1 --batch --ignore-whitespace < ../patch-patch-{KERNEL_MAJOR}.{KERNEL_MINOR}.14 1>/dev/null; 
#sed -i -e "s/SUBLEVEL \= 14/SUBLEVEL \= 0/g" Makefile;
#
#
##############################################################################################################################
# Configuration du Noyau #
##########################
# Configuration actuelle du Noyau
rm .config 2>/dev/null; cp /boot/config-$(uname -r) .config;
#
# Fix Erreur
sed -i -e "s/^CONFIG_ANDROID_BINDER_IPC\=m/CONFIG_ANDROID_BINDER_IPC\=n/g" .config;
sed -i -e "s/^CONFIG_BASE_SMALL\=0/CONFIG_BASE_SMALL\=n/g"                 .config;
sed -i -e "s/^CONFIG_FSCACHE\=m/CONFIG_FSCACHE\=y/g"                       .config;
sed -i -e "s/^CONFIG_VFIO_VIRQFD\=m/CONFIG_VFIO_VIRQFD\=y/g"               .config;
#
##############################################################################################################################
# Mettre à jour la configuration avec oldconfig #
#################################################
#
# Pour intégrer les nouvelles options du noyau tout en conservant tes choix précédents.
yes "" | make oldconfig 1>/dev/null;
#
# Verification
grep -E "^CONFIG_ANDROID_BINDER_IPC|^CONFIG_BASE_SMALL|^CONFIG_FSCACHE|^CONFIG_VFIO_VIRQFD" .config |sort -V
#
##############################################################################################################################
# Compilation #
###############
# Nettoyage du noyaux
make clean;
#
# 8 Go + Multithreading
echo "# ------------------------------------------------------"   > Compilation;
echo "# Début de la compilation: $(date +'%d/%m/%y %H:%M')"      >> Compilation;
echo "# ------------------------------------------------------"  >> Compilation;
echo ""                                                          >> Compilation;
echo ""                                                          >> Compilation;
prlimit --as=1073741824 make -j$(( $(nproc) - 2 ))               >> Compilation;
echo ""                                                          >> Compilation;
echo ""                                                          >> Compilation;
echo "# ------------------------------------------------------"  >> Compilation;
echo "# Fin de la compilation: $(date +'%d/%m/%y %H:%M')"        >> Compilation;
echo "# ------------------------------------------------------"  >> Compilation;
tail -f Compilation;

##############################################################################################################################
```

```
VERSION = 6
PATCHLEVEL = 10
SUBLEVEL = 14
```

<br />

### B. Récupérer sa configuration du Noyau
La commande suivante permet de récupérer la configuration de son noyau.
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
#### 1. Ouvrir le menu
```bash
#############################################################################################################
clear;
make menuconfig;
#############################################################################################################
```

#### 3. Rechercher (Fix erreur)
Pour trouver un paramètre dans l'interface Menuconfig, faire la touche `MAJ+/` et rechercher le termes ou la variables.

Puis éditer le fichier de configuration pour corriger l'erreur.

![image](https://github.com/user-attachments/assets/90fef997-10c6-4592-8987-c75c931f82f6)



#### 3. Afficher le menu caché
Taper sur la touche `Z`


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


