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
# Patch #
#########
patch -p1 --dry-run < ../patch-$KERNEL.1;

############################################################################################################
grep CONFIG_OPTION /boot/config-$(uname -r)

############################################################################################################
make -j$(nproc) mrproper;
make -j$(nproc) oldconfig;
make -j$(nproc) menuconfig;
make -j$(nproc) oldconfig;
make -j$(nproc) prepare;

#cp /boot/config-$(uname -r) .config;

############################################################################################################
make -j11 bzImage;
make -j11 modules;

############################################################################################################
# Installation #
################
sudo make -j$(nproc) modules_install;
sudo make -j$(nproc) install;

# Optionnel
sudo make -j$(nproc) headers_install;


############################################################################################################
sudo update-initramfs -c -k 6.15;
sudo update-grub;
############################################################################################################
```
