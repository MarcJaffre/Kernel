```bash
##############################################################################################################################
# Presentation:
# - Patchage du Kernel
##############################################################################################################################

##############################################################################################################################
# Nettoyage console #
#####################
clear;
#
##############################################################################################################################
# Variables d-environnement #
#############################
KERNEL_MAJOR="6"
KERNEL_MINOR="10"

##############################################################################################################################
# Dossier de Travail #
######################
cd /Data/kernel/linux-${KERNEL_MAJOR}.${KERNEL_MINOR};
#
##############################################################################################################################
```

<br />

### Simuler le patch
Permet de déceler des erreurs car il n'affiche que les erreurs.
```bash
clear;
for i in $(ls ../patch-* | xargs -n 1 basename | grep -E "^patch-${KERNEL_MAJOR}+\.${KERNEL_MINOR}+\.[0-9]+$" | sort -V); do
  echo $i
  patch --dry-run -p1 --batch --ignore-whitespace < ../$i 1>/dev/null;
done
```

<br />


### Appliquer Patch
```bash
##############################################################################################################################
# Nettoyage console #
#####################
clear;
#
##############################################################################################################################
# Patch 6.10.1 #
################
# Erreurs de compilation avec certains modules
patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.1 1>/dev/null;  make kernelversion;
#sed -i -e "s/SUBLEVEL \= 1/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.2 #
################
# Problèmes de performance et de compilation persistants
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.2 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 2/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.3 #
################
# Pas de résolution des bugs de compilation/performance signalés
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.3 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 3/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.4 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.4 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 4/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.5 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.5 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 5/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.6 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.6 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 6/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.7 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.7 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 7/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.8 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.8 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 8/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.9 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.9 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 9/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.10 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.10 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 10/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.11 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.11 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 11/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.12 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.12 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 12/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.13 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.13 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 13/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.14 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.14 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 14/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
```

<br />

<br />


```bash
##############################################################################################################################
# Amelioration
# - Message
# - s/^CONFIG_ANDROID_BINDER_IPC=.*/CONFIG_ANDROID_BINDER_IPC=n/
##############################################################################################################################

##############################################################################################################################
# Message #
###########
#echo "#################################";
#echo "#       Patchage du Kernel      #";
#echo "#################################";
#echo "#                               #";
#echo "# Kernel d'Originel : $(make kernelversion)    #";
#echo "#                               #";
#echo "# Patch : $(make kernelversion)                #";
#echo "#                               #";
#echo "# Final : $(make kernelversion)               #";
#echo "#                               #";
#echo "#################################";
#echo "";
##############################################################################################################################
```
