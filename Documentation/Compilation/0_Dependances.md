
### A. Installer les paquets
```bash
clear;
apt-get update                  1>/dev/null;
apt install -y build-essential  1>/dev/null;
apt install -y curl             1>/dev/null;
apt install -y fakeroot         1>/dev/null;
apt install -y git              1>/dev/null;

apt install -y libbpf-dev       1>/dev/null;
apt install -y libelf-dev       1>/dev/null;
apt install -y libcrypto++-dev  1>/dev/null;
apt install -y libdevmapper-dev 1>/dev/null;
apt install -y libgcc-$(gcc -v 2>&1 | grep '^gcc version' | cut -d' ' -f3 | cut -d "." -f 1)-dev 1>/dev/null;

apt install -y libglade2-dev     1>/dev/null;
apt install -y libgtk2.0-dev     1>/dev/null;

apt install -y libieee1284-3-dev 1>/dev/null;
apt install -y liblz4-dev        1>/dev/null;
apt install -y liblzma-dev       1>/dev/null;
apt install -y libncurses-dev    1>/dev/null;
#apt install -y libqt4-dev       1>/dev/null;
apt install -y libpci-dev        1>/dev/null;
apt install -y libssl-dev        1>/dev/null;
apt install -y libusb-dev        1>/dev/null;
apt install -y libz-dev          1>/dev/null;

apt install -y linux-headers-$(uname -r)                    1>/dev/null;
apt install -y linux-source-$(uname -r | cut -d "." -f 1-2) 1>/dev/null;

apt install -y ncurses-dev       1>/dev/null;
```

<br />

### B. Dépendance
```bash
# Requis si variable DEBUG_INFO_BTF = Y
apt install -y pahole;
```
