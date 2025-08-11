https://cloudspinx.com/install-linux-kernel-6-15-on-debian/

### A. Check Kernel
uname -r

### B. Upgrade OS
apt update;
apt install -y wget gnupg2;
apt upgrade -y;

### C. Package
sudo apt install -y build-essential dwarves python3 libncurses-dev flex bison libssl-dev bc libelf-dev

### D. Kernel 6.15.1
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.15.1.tar.xz
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.15.1.tar.sign
tar -xvf linux-6.15.1.tar.xz

### D. Check Sign
gpg --verify -vvvv linux-6.15.1.tar.sign
gpg --search-keys 38DBBDC86092693E

### E. Config
cd linux-6.15.1
sudo cp -v /boot/config-$(uname -r) .config

### F. Custom (Save > Exit)
sudo make menuconfig 

### G. Compilation
sudo make bzImage

### H. Fix error : debian-uefi-certs.pem
make localmodconfig
sudo make bzImage

### I. Install
sudo make modules
sudo make modules_install
sudo make install

### J. Grub
sudo update-grub

### K. Reboot
sudo reboot -i

### L. Check Kernel
uname -a

# Update
apt update
apt upgrade -y
