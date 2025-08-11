----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------# <p align='center'> NON FONCTIONNEL </p>

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## I. Compilation du kernel 6.15
## A. Information du kernel 6.12
```bash
# uname -r
6.12.38+deb13-amd64

# ls /lib/modules/$(uname -r)

# lsmod | grep -v 0; # Module charge et utilise
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
```



<br />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## II.

- **Configuration de base :**  
  Faites un `make oldconfig` à partir de votre configuration actuelle (`/boot/config-$(uname -r)`) pour garder les options compatibles avec votre système actuel. Puis lancez `make menuconfig` pour ajuster manuellement si besoin.

- **Modules spécifiques :**  
  Si vous utilisez des modules tiers ou DKMS (comme amdgpu, rtl88x2bu, nvidia), assurez-vous que la configuration du kernel les supporte (ex. options PCI, DRM, crypto, etc.) et que les en-têtes (`linux-headers`) soient bien installés. Sur certains kernel 6.12, des incompatibilités DKMS ont été reportées, notamment le message d'erreur `dma_resv->seq is missing` dans les builds amdgpu. Il faut alors :
  
  - Soit utiliser un kernel stable reconnu compatible (comme 6.11 ou 6.14).
  - Soit patcher ou attendre la mise à jour des modules tiers.
  
- **Options importantes à activer dans le kernel config :**  
  - Sous-menu `Processor type and features` :  
    - Votre architecture AMD64 doit être bien sélectionnée.  
    - Activer `Preemption Model` si vous cherchez de la faible latence ou temps réel (par exemple `Preemptible Kernel (Low-Latency Desktop)` ou `Fully Preemptible Kernel (RT)` si besoin).[9]
  - Sous-menu `Device Drivers` :  
    - Activer les pilotes nécessaires à vos composants (ex. `SCSI`, `PCI`, `USB`, `AHCI` pour disque, `Sound` pour audio).  
    - Activer `CONFIG_MODULES` pour le support des modules.  
  - Sous-menu `Cryptographic API` si vous avez des modules liés à la crypto (ex. AES-NI).  
  - Réseau, filesystem (ext4, vfat, etc.) selon usages.

- **Avant compilation :**  
  - Faites un `make mrproper` pour nettoyer.  
  - Puis `make oldconfig` pour réutiliser la config existante.  
  - Enfin `make menuconfig` pour ajuster.

- **Compilation et installation :**  
  Votre procédure est correcte : compilation du `bzImage`, des `modules`, puis `modules_install` et `install`, mise à jour de l’`initramfs` et de grub.

- **Problèmes fréquents et solutions :**  
  - Certains modules DKMS ne se compilent pas avec le kernel 6.12.x sur Debian, notamment amdgpu et d'autres modules tiers, ce qui peut nécessiter de rester sur un kernel supporté (6.11 ou 6.14) ou de patcher les modules.[2][1]
  - Veillez à ce que `/usr/src/linux-headers-$(uname -r)` soit bien installé et synchronisé avec le kernel compilé.  
  - Si vous avez un problème avec les modules DKMS, vérifiez avec `dkms status` et supprimez ou réinstallez les modules problématiques.

En résumé, la configuration du kernel dépend grandement des modules que vous souhaitez utiliser, mais pour un fonctionnement basique :  
- Activez l’architecture amd64, modules, préemption si besoin, pilotes matériels courants, système de fichiers.  
- Assurez-vous de la compatibilité avec les modules DKMS que vous utilisez (éviter les kernel versions où ils posent problème).  
- Synchronisez correctement headers et config pour éviter les erreurs lors de la compilation.

Si vous rencontrez des erreurs spécifiques à un module ou à la compilation, elles peuvent guider les options précises à modifier dans le menuconfig.
