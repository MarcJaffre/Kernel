https://cloudspinx.com/install-linux-kernel-6-15-on-debian/

### A. Check Kernel
```bash
clear;
uname -r;
```

### B. Upgrade OS
```bash
clear;
apt update;
apt install -y wget gnupg2;
apt upgrade -y;
```

### C. Package
```bash
clear;
sudo apt install -y build-essential dwarves python3 libncurses-dev flex bison libssl-dev bc libelf-dev;
```

### D. Kernel 6.15.1
```bash
clear;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.15.1.tar.xz;
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.15.1.tar.sign;
tar -xvf linux-6.15.1.tar.xz
```

### E. Check Sign
```bash
clear;
gpg --verify -vvvv linux-6.15.1.tar.sign;
gpg --search-keys 38DBBDC86092693E;
```

### F. Config
```bash
clear;
cd linux-6.15.1
sudo cp -v /boot/config-$(uname -r) .config;
```

### G. Custom (Save > Exit)
```bash
clear;
sudo make menuconfig;
```

### H. Compilation
```bash
clear;
sudo make bzImage;
```

### I. Fix error : debian-uefi-certs.pem
```bash
clear;
make localmodconfig;
sudo make bzImage;
```

### J. Install
```bash
clear;
sudo make modules;
sudo make modules_install;
sudo make install;
```

### K. Grub
```bash
clear;
sudo update-grub;
```

### L. Reboot
```bash
clear;
sudo reboot -i;
```

### M. Check Kernel
```bash
clear;
uname -a;
```

### N. Update
```bash
clear;
apt update;
apt upgrade -y;
```
