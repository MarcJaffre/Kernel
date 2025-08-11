### A. Download
```bash
clear;
WORKDIR=/mnt/data/kernel
KERNEL=6.15

cd $HOME;
mkdir -p $WORKDIR;
cd $WORKDIR;

wget https://www.kernel.org/pub/linux/kernel/v6.x/linux-$KERNEL.tar.xz  2>/dev/null;
unxz patch-$KERNEL.xz;
# for i in $(ls *.xz);do unxz $i; done
```


### B. Compilation
```bash
clear;

cd $WORKDIR;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.1;
# patch -p1 -R < ../patch-$KERNEL.1 | grep -v "patching file";
make kernelversion;
```










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
```
