### A. Kernel 6.18.X (Réussi)
#### 1. Documentation
https://docs.kernel.org/process/applying-patches.html
#### 2. Kernel et Patch
Les patchs du dossier `vY.x` ne sont pas des incrémentials. On applique le patch 6.18.1.
#### 2. Patch incrémentiel
Le kernel est en `6.18.1` puis on fait une montée de version par patch. (Exemple: `6.18.1` -> `6.18.2` > .... > `6.18.15`)

```bash
# ===================================================================================
clear;
cd       $HOME;
rm    -r $HOME/kernel 2>/dev/null;
mkdir -p $HOME/kernel;
cd       $HOME/kernel;

# ===================================================================================
# Kernel 6.18.0 puis patch 6.18.1
clear;
wget -q https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.18.tar.xz;
wget -q https://cdn.kernel.org/pub/linux/kernel/v6.x/patch-6.18.1.xz;

# ===================================================================================
# Patch incrementiel (Le patch 6.18.0 vers 6.18.1 n'existe pas)
clear;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.1-2.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.2-3.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.3-4.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.4-5.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.5-6.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.6-7.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.7-8.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.8-9.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.9-10.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.10-11.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.11-12.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.12-13.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.13-14.xz;
wget -q https://www.kernel.org/pub/linux/kernel/v6.x/incr/patch-6.18.14-15.xz;

# ===================================================================================
clear;
rm -r linux-6.18 2>/dev/null;
for files in $(ls *.xz);  do unxz   $files; done
for files in $(ls *.tar); do tar xf $files; done


# ===================================================================================
clear;
cd linux-6.18;


# ===================================================================================
# Patchage 6.18.1 (v6.x)
clear;
patch -p1 < ../patch-6.18.1;     make kernelversion;

# ===================================================================================
# Patchage incremental
patch -p1 < ../patch-6.18.1-2;   make kernelversion;
patch -p1 < ../patch-6.18.2-3;   make kernelversion;
patch -p1 < ../patch-6.18.3-4;   make kernelversion;
patch -p1 < ../patch-6.18.4-5;   make kernelversion;
patch -p1 < ../patch-6.18.5-6;   make kernelversion;
patch -p1 < ../patch-6.18.6-7;   make kernelversion;
patch -p1 < ../patch-6.18.7-8;   make kernelversion;
patch -p1 < ../patch-6.18.8-9;   make kernelversion;
patch -p1 < ../patch-6.18.9-10;  make kernelversion;
patch -p1 < ../patch-6.18.10-11; make kernelversion;
patch -p1 < ../patch-6.18.11-12; make kernelversion;
patch -p1 < ../patch-6.18.12-13; make kernelversion;
patch -p1 < ../patch-6.18.13-14; make kernelversion;
patch -p1 < ../patch-6.18.14-15; make kernelversion;

# ===================================================================================
# Nettoyage pré‑compilation
clear;
make clean;

# ===================================================================================
# Configure tes options
clear;
make menuconfig;

# ===================================================================================
# Compile
clear;
make -j$(nproc) all;

# ===================================================================================
# Creation des modules
clear;
make modules_install;

# ===================================================================================
# Installation du Kernel
clear;
make install;
```
