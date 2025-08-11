# <p align='center'> NON FONCTIONNEL </p>


### A. Download
```bash
clear;
#############################################################################################
# VARIABLES #
#############
WORKDIR=/mnt/data/kernel
KERNEL=6.15
#############################################################################################
# WORKDIR #
###########
cd       $HOME;
rm -r    $WORKDIR 2>/dev/null;
mkdir -p $WORKDIR;
cd       $WORKDIR;

#############################################################################################
# Download #
############
wget https://www.kernel.org/pub/linux/kernel/v6.x/linux-$KERNEL.tar.xz  2>/dev/null;

#############################################################################################
# EXTRACT #
###########
tar xf ./linux-$KERNEL.tar.xz;

#############################################################################################
```

<br />

### B. Compilation
```bash
clear;
#############################################################################################
# WORKDIR #
###########
cd $WORKDIR/linux-$KERNEL;

#############################################################################################
# Configuration #
#################
make mrproper;
make oldconfig;
make menuconfig;
make oldconfig;
make prepare;

#############################################################################################
# Compilation #
###############
make -j11 bzImage;
make -j11 modules;

#############################################################################################
# Installation #
################
sudo make modules_install;
sudo make install;

#############################################################################################
# Demarrage #
#############
clear;
sudo update-initramfs -c -k 6.15;
sudo update-grub;
#############################################################################################
#############################################################################################
#############################################################################################
```



<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />

---------------------------------------------


```
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.xz      2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.1.xz    2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.2.xz    2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.3.xz    2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.4.xz    2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.5.xz    2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.6.xz    2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.7.xz    2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.8.xz    2>/dev/null;
# wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.9.xz    2>/dev/null;

# unxz patch-$KERNEL.1.xz;
# unxz patch-$KERNEL.2.xz;
# unxz patch-$KERNEL.3.xz;
# unxz patch-$KERNEL.4.xz;
# unxz patch-$KERNEL.5.xz;
# unxz patch-$KERNEL.6.xz;
# unxz patch-$KERNEL.7.xz;
# unxz patch-$KERNEL.8.xz;
# unxz patch-$KERNEL.9.xz;
# for i in $(ls *.xz);do unxz $i; done;

#cp /boot/config-$(uname -r) .config;
```
