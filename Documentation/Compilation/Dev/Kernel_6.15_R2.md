# <p align='center'> NON FONCTIONNEL </p>

### A. Download
```bash
clear;
############################################################################################################
KERNEL=6.15
WORKDIR=/mnt/data/kernel
############################################################################################################
cd $HOME;
rm -r $WORKDIR 2>/dev/null;
mkdir -p $WORKDIR;
cd $WORKDIR;
############################################################################################################
wget https://www.kernel.org/pub/linux/kernel/v6.x/linux-$KERNEL.tar.xz  2>/dev/null;
############################################################################################################
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.xz      2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.1.xz    2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.2.xz    2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.3.xz    2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.4.xz    2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.5.xz    2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.6.xz    2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.7.xz    2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.8.xz    2>/dev/null;
wget https://www.kernel.org/pub/linux/kernel/v6.x/patch-$KERNEL.9.xz    2>/dev/null;
############################################################################################################
tar xf ./linux-$KERNEL.tar.xz;
unxz patch-$KERNEL.xz;
unxz patch-$KERNEL.1.xz;
unxz patch-$KERNEL.2.xz;
unxz patch-$KERNEL.3.xz;
unxz patch-$KERNEL.4.xz;
unxz patch-$KERNEL.5.xz;
unxz patch-$KERNEL.6.xz;
unxz patch-$KERNEL.7.xz;
unxz patch-$KERNEL.8.xz;
unxz patch-$KERNEL.9.xz;

############################################################################################################
clear;
cd $WORKDIR/linux-$KERNEL;

############################################################################################################
patch -p1 < ../patch-$KERNEL.1;


############################################################################################################
grep CONFIG_OPTION /boot/config-$(uname -r)

############################################################################################################
make mrproper;
#cp /boot/config-$(uname -r) .config;
make oldconfig;
make menuconfig;
make oldconfig;
make prepare;


############################################################################################################
make -j11 bzImage;
make -j11 modules;

############################################################################################################
# Installation #
################
#sudo make headers_install; # Optionnel
sudo make modules_install;
sudo make install;

############################################################################################################
sudo update-initramfs -c -k 6.15;
sudo update-grub;
############################################################################################################
```
