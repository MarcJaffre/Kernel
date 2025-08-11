# <p align='center'> NON FONCTIONNEL </p>

## A. Information sur le Kernel 6.12
```bash
# uname -r
6.12.38+deb13-amd64

# lsmod | awk '{print $1}' | sort -n
aesni_intel
ahci
autofs4
binfmt_misc
bochs
button
ccp
cdrom
configfs
crc16
crc32c_generic
crc32c_intel
crc32_pclmul
crct10dif_pclmul
cryptd
crypto_simd
dm_mod
drm
drm_kms_helper
drm_ttm_helper
drm_vram_helper
e1000
efi_pstore
efivarfs
ehci_hcd
ehci_pci
evdev
ext4
fat
gf128mul
ghash_clmulni_intel
i2c_i801
i2c_smbus
inet_diag
intel_pmc_bxt
intel_rapl_common
intel_rapl_msr
ip_tables
irqbypass
iTCO_vendor_support
iTCO_wdt
jbd2
joydev
kvm
kvm_amd
libahci
libata
lp
lpc_ich
mbcache
Module
mptcp_diag
msr
nfnetlink
nls_ascii
nls_cp437
parport
parport_pc
pcspkr
ppdev
psmouse
qemu_fw_cfg
qrtr
raw_diag
rfkill
scsi_common
scsi_mod
sd_mod
serio_raw
sg
sha1_ssse3
sha256_ssse3
sha512_ssse3
snd
snd_hda_codec
snd_hda_core
snd_hda_intel
snd_hrtimer
snd_hwdep
snd_intel_dspcfg
snd_intel_sdw_acpi
snd_pcm
snd_seq
snd_seq_device
snd_seq_dummy
snd_timer
soundcore
sr_mod
tcp_diag
tls
ttm
udp_diag
uhci_hcd
unix_diag
usb_common
usbcore
vfat
vmw_vmci
vmw_vsock_virtio_transport_common
vmw_vsock_vmci_transport
vsock
vsock_diag
vsock_loopback
watchdog
x_tables
```


### B. Téléchargement
Télécharge le Kernel 6.15.
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

### C. Compilation (KO)
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
##########
