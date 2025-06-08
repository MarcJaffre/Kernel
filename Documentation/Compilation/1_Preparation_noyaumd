------------------------------------------------------------------------------------------------------------------------------
# <p align='center'> Téléchargement du Kernel </p>
------------------------------------------------------------------------------------------------------------------------------
```bash
##############################################################################################################################
# Presentation:
# - Telecharge le Kernel 6.10.0
# - Telecharge les patchs (v1 a v14)
# - Patchage du Kernel
##############################################################################################################################

##############################################################################################################################
# Amelioration
# - s/^CONFIG_ANDROID_BINDER_IPC=.*/CONFIG_ANDROID_BINDER_IPC=n/
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
URL="https://cdn.kernel.org/pub/linux/kernel/v${KERNEL_MAJOR}.x/"
URL_KERNEL="$URL/linux-${KERNEL_MAJOR}.${KERNEL_MINOR}.tar.xz"
#
##############################################################################################################################
# Dossier de Travail #
######################
cd /Data;
rm -r kernel 2>/dev/null;
mkdir kernel 2>/dev/null;
cd kernel;
#
##############################################################################################################################
# Telechargement du Kernel #
############################
wget ${URL_KERNEL} 2>/dev/null;
#
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
#
##############################################################################################################################
# Patch 6.10.1 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.1 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 1/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.2 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.2 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 2/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.3 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.3 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 3/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.4 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.4 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 4/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.5 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.5 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 5/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.6 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.6 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 6/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.7 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.7 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 7/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.8 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.8 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 8/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.9 #
################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.9 1>/dev/null;
#echo "# Patch : $(make kernelversion)                #";
#sed -i -e "s/SUBLEVEL \= 9/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.10 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.10 1>/dev/null;
#echo "# Patch : $(make kernelversion)               #";
#sed -i -e "s/SUBLEVEL \= 10/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.11 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.11 1>/dev/null;
#echo "# Patch : $(make kernelversion)               #";
#sed -i -e "s/SUBLEVEL \= 11/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.12 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.12 1>/dev/null;
#echo "# Patch : $(make kernelversion)               #";
#sed -i -e "s/SUBLEVEL \= 12/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.13 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.13 1>/dev/null;
#echo "# Patch : $(make kernelversion)               #";
#sed -i -e "s/SUBLEVEL \= 13/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
# Patch 6.10.14 #
#################
#patch -p1 --batch --ignore-whitespace < ../patch-${KERNEL_MAJOR}.${KERNEL_MINOR}.14 1>/dev/null;
#sed -i -e "s/SUBLEVEL \= 14/SUBLEVEL \= 0/g" Makefile;
#
##############################################################################################################################
echo "#                               #";
echo "# Final : $(make kernelversion)               #";
echo "#                               #";
echo "#################################";
echo "";
##############################################################################################################################
```
