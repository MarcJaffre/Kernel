```bash
clear;

WORKDIR=/mnt/data/kernel
KERNEL=6.15

cd $HOME;
mkdir -p $WORKDIR;
cd $WORKDIR;

wget https://www.kernel.org/pub/linux/kernel/v6.x/linux-$KERNEL.tar.xz  2>/dev/null;
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
```


# Patch 1
```bash
clear;
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.1;
# patch -p1 -R < ../patch-$KERNEL.1 | grep -v "patching file";
make kernelversion;
```
# Patch 2
```bash
clear;
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.2;
# patch -p1 -R < ../patch-$KERNEL.2 | grep -v "patching file";
make kernelversion;
```
# Patch 3
```bash
clear;
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.3;
# patch -p1 -R < ../patch-$KERNEL.3 | grep -v "patching file";
make kernelversion;
```

# Patch 4
```bash
clear;
cd $WORKDIR;
WORKDIR=/mnt/data/kernel;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.4;
# patch -p1 -R < ../patch-$KERNEL.4 | grep -v "patching file";
make kernelversion;
```

# Patch 5
```bash
clear;
cd $WORKDIR;
WORKDIR=/mnt/data/kernel;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.5;
# patch -p1 -R < ../patch-$KERNEL.5 | grep -v "patching file";
make kernelversion;
```

# Patch 6
```bash
clear;
cd $WORKDIR;
WORKDIR=/mnt/data/kernel;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.6;
# patch -p1 -R < ../patch-$KERNEL.6 | grep -v "patching file";
make kernelversion;
```

# Patch 7
```bash
clear;
cd $WORKDIR;
WORKDIR=/mnt/data/kernel;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.7;
# patch -p1 -R < ../patch-$KERNEL.7 | grep -v "patching file";
make kernelversion;
```

# Patch 8
```bash
clear;
cd $WORKDIR;
WORKDIR=/mnt/data/kernel;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.8;
# patch -p1 -R < ../patch-$KERNEL.8 | grep -v "patching file";
make kernelversion;
```

# Patch 9
```bash
clear;
cd $WORKDIR;
WORKDIR=/mnt/data/kernel;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.9;
# patch -p1 -R < ../patch-$KERNEL.9 | grep -v "patching file";
make kernelversion;
```






# General
```bash
clear;
cd $WORKDIR;
WORKDIR=/mnt/data/kernel;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
```




```bash
patch -p1 --dry-run -t < ../patch-$KERNEL.1;
patch -p1  -t    < ../patch-$KERNEL.1;
patch -p1 -R -t  < ../patch-$KERNEL.1;
make kernelversion;


patch -p1 --dry-run -t < ../patch-$KERNEL.2;
patch -p1 -t    < ../patch-$KERNEL.2;
patch -p1 -R -t < ../patch-$KERNEL.2;
make kernelversion;


patch -p1 --dry-run -t < ../patch-$KERNEL.2;
patch -p1 -t    < ../patch-$KERNEL.2;
patch -p1 -R -t < ../patch-$KERNEL.2;
make kernelversion;


patch -p1 --dry-run -t < ../patch-$KERNEL.3;
patch -p1 -t    < ../patch-$KERNEL.3;
patch -p1 -R -t < ../patch-$KERNEL.3;
make kernelversion;

patch -p1 --dry-run -t < ../patch-$KERNEL.4;
patch -p1    < ../patch-$KERNEL.4;
patch -p1 -R < ../patch-$KERNEL.4;
make kernelversion;


patch -p1 --dry-run -t < ../patch-$KERNEL.5;
patch -p1    < ../patch-$KERNEL.5;
patch -p1 -R < ../patch-$KERNEL.5;
make kernelversion;


patch -p1 --dry-run -t < ../patch-$KERNEL.6;
patch -p1    < ../patch-$KERNEL.6;
patch -p1 -R < ../patch-$KERNEL.6;
make kernelversion;


patch -p1 --dry-run -t < ../patch-$KERNEL.7;
patch -p1 -t    < ../patch-$KERNEL.7;
patch -p1 -R -t < ../patch-$KERNEL.7;
make kernelversion;


patch -p1 --dry-run -t < ../patch-$KERNEL.8;
patch -p1 -t    < ../patch-$KERNEL.8;
patch -p1 -R -t < ../patch-$KERNEL.8;
make kernelversion;


patch -p1 --dry-run -t < ../patch-$KERNEL.9;
patch -p1 -t    < ../patch-$KERNEL.9;
patch -p1 -R -t < ../patch-$KERNEL.9;
make kernelversion;
```
