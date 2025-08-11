# <p align='center'> NON FONCTIONNEL </p>

## A. Information sur le Kernel 6.12
```bash
# uname -r
6.12.38+deb13-amd64

# ls /lib/modules/$(uname -r)

# lsmod | grep -v 0
Module                  Size  Used by
inet_diag              28672  4 tcp_diag,mptcp_diag,raw_diag,udp_diag
snd_hrtimer            12288  1
snd_seq_device         16384  1 snd_seq
qrtr                   57344  2
binfmt_misc            28672  1
nls_ascii              12288  1
nls_cp437              16384  1
vfat                   24576  1
intel_rapl_common      53248  1 intel_rapl_msr
kvm                  1396736  1 kvm_amd
snd_intel_sdw_acpi     16384  1 snd_intel_dspcfg
irqbypass              12288  1 kvm
snd_pcm               188416  3 snd_hda_intel,snd_hda_codec,snd_hda_core
gf128mul               16384  1 aesni_intel
snd_timer              53248  3 snd_seq,snd_hrtimer,snd_pcm
snd                   151552  9 snd_seq,snd_seq_device,snd_hwdep,snd_hda_intel,snd_hda_codec,snd_timer,snd_pcm
crypto_simd            16384  1 aesni_intel
cryptd                 28672  2 crypto_simd,ghash_clmulni_intel
soundcore              16384  1 snd
evdev                  28672  6
configfs               69632  1
efivarfs               28672  1
x_tables               53248  1 ip_tables
autofs4                57344  2
ext4                 1142784  4
crc16                  12288  1 ext4
mbcache                16384  1 ext4
dm_mod                221184  9
bochs                  16384  1
drm_vram_helper        28672  1 bochs
drm_ttm_helper         16384  3 bochs,drm_vram_helper
drm_kms_helper        253952  3 bochs,drm_vram_helper,drm_ttm_helper
ahci                   49152  6
libata                462848  2 libahci,ahci
iTCO_wdt               16384  1
drm                   774144  7 drm_kms_helper,bochs,drm_vram_helper,drm_ttm_helper,ttm
intel_pmc_bxt          16384  1 iTCO_wdt
iTCO_vendor_support    12288  1 iTCO_wdt
watchdog               49152  1 iTCO_wdt
crc32c_intel           16384  8
scsi_common            16384  5 scsi_mod,sd_mod,libata,sg,sr_mod
usb_common             16384  3 usbcore,ehci_hcd,uhci_hcd
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
