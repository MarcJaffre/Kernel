------------------------------------------------------------------------------------------------------------------------------
# <p align='center'> Compilation du noyaux </p>
------------------------------------------------------------------------------------------------------------------------------


```bash
##############################################################################################################################
#
# Presentation:
# - Copier la configuration de la machine dans la source du noyau
# - Correctif bug du fichier config
# - Mise a jour de la configuration du noyau Linux
# - Nettoyage du noyau
# - Compilation avec compte rendu
#
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
#
##############################################################################################################################
# Dossier de Travail #
######################
cd /Data/kernel/linux-${KERNEL_MAJOR}.${KERNEL_MINOR};
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
