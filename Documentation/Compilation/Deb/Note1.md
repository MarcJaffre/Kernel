
Un logiciel Diff pour comparer le contenue ! (kdiff3, meld)


```log
patching file Makefile

patching file arch/arm64/boot/dts/intel/socfpga_agilex5.dtsi
patching file arch/arm64/boot/dts/qcom/ipq9574.dtsi
patching file arch/arm64/boot/dts/qcom/sa8775p.dtsi
patching file arch/arm64/boot/dts/qcom/sm8350.dtsi
patching file arch/arm64/boot/dts/qcom/sm8450.dtsi
patching file arch/arm64/boot/dts/qcom/sm8550.dtsi
patching file arch/arm64/boot/dts/qcom/sm8650.dtsi
patching file arch/arm64/boot/dts/qcom/x1e001de-devkit.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-asus-vivobook-s15.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-dell-xps13-9345.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-hp-omnibook-x14.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-lenovo-yoga-slim7x.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-qcp.dts
patching file arch/arm64/boot/dts/qcom/x1e80100.dtsi
patching file arch/arm64/boot/dts/rockchip/rk3399-puma.dtsi
patching file arch/arm64/boot/dts/rockchip/rk3576.dtsi
patching file arch/arm64/boot/dts/ti/k3-am62-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-am62a-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-am62p-j722s-common-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-am62x-sk-csi2-imx219.dtso
patching file arch/arm64/boot/dts/ti/k3-am62x-sk-csi2-ov5640.dtso
patching file arch/arm64/boot/dts/ti/k3-am62x-sk-csi2-tevi-ov5640.dtso
patching file arch/arm64/boot/dts/ti/k3-am65-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-am68-sk-base-board.dts
patching file arch/arm64/boot/dts/ti/k3-j721e-sk-csi2-dual-imx219.dtso
patching file arch/arm64/boot/dts/ti/k3-j721e-sk.dts
patching file arch/arm64/boot/dts/ti/k3-j722s-evm.dts
patching file arch/arm64/boot/dts/ti/k3-j722s-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-j784s4-j742s2-main-common.dtsi

patching file drivers/iommu/iommu.c
patching file drivers/perf/arm-cmn.c
patching file fs/coredump.c
patching file fs/pidfs.c
patching file include/linux/coredump.h
patching file include/linux/iommu.h
patching file net/sched/sch_hfsc.c
```

<br />


# Patch 2
Le patch 2 inclus le patch 1
```bash
clear;
KERNEL=6.15
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
patch -p1 -t < ../patch-$KERNEL.2;
# patch -p1 -R < ../patch-$KERNEL.2 | grep -v "patching file";
make kernelversion;
```


```log
patching file Documentation/devicetree/bindings/phy/fsl,imx8mq-usb-phy.yaml
patching file Documentation/devicetree/bindings/pwm/adi,axi-pwmgen.yaml
patching file Documentation/devicetree/bindings/remoteproc/qcom,sm8150-pas.yaml
patching file Documentation/devicetree/bindings/usb/cypress,hx3.yaml
patching file Documentation/firmware-guide/acpi/dsd/data-node-references.rst
patching file Documentation/firmware-guide/acpi/dsd/graph.rst
patching file Documentation/firmware-guide/acpi/dsd/leds.rst
patching file Makefile

patching file arch/arm64/boot/dts/intel/socfpga_agilex5.dtsi
patching file arch/arm64/boot/dts/qcom/ipq9574.dtsi
patching file arch/arm64/boot/dts/qcom/sa8775p.dtsi
patching file arch/arm64/boot/dts/qcom/sm8350.dtsi
patching file arch/arm64/boot/dts/qcom/sm8450.dtsi
patching file arch/arm64/boot/dts/qcom/sm8550.dtsi
patching file arch/arm64/boot/dts/qcom/sm8650.dtsi
patching file arch/arm64/boot/dts/qcom/x1e001de-devkit.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-asus-vivobook-s15.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-dell-xps13-9345.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-hp-omnibook-x14.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-lenovo-yoga-slim7x.dts
patching file arch/arm64/boot/dts/qcom/x1e80100-qcp.dts
patching file arch/arm64/boot/dts/qcom/x1e80100.dtsi
patching file arch/arm64/boot/dts/rockchip/rk3399-puma.dtsi
patching file arch/arm64/boot/dts/rockchip/rk3576.dtsi
patching file arch/arm64/boot/dts/ti/k3-am62-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-am62a-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-am62p-j722s-common-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-am62x-sk-csi2-imx219.dtso
patching file arch/arm64/boot/dts/ti/k3-am62x-sk-csi2-ov5640.dtso
patching file arch/arm64/boot/dts/ti/k3-am62x-sk-csi2-tevi-ov5640.dtso
patching file arch/arm64/boot/dts/ti/k3-am65-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-am68-sk-base-board.dts
patching file arch/arm64/boot/dts/ti/k3-j721e-sk-csi2-dual-imx219.dtso
patching file arch/arm64/boot/dts/ti/k3-j721e-sk.dts
patching file arch/arm64/boot/dts/ti/k3-j722s-evm.dts
patching file arch/arm64/boot/dts/ti/k3-j722s-main.dtsi
patching file arch/arm64/boot/dts/ti/k3-j784s4-j742s2-main-common.dtsi

patching file arch/x86/kernel/smpboot.c
patching file drivers/acpi/acpica/acdebug.h
patching file drivers/acpi/acpica/aclocal.h
patching file drivers/acpi/acpica/nsnames.c
patching file drivers/acpi/acpica/nsrepair2.c
patching file drivers/android/binder.c
patching file drivers/android/binder_internal.h
patching file drivers/android/binderfs.c
patching file drivers/bluetooth/hci_qca.c
patching file drivers/clk/samsung/clk-exynosautov920.c
patching file drivers/cpufreq/acpi-cpufreq.c
patching file drivers/gpu/drm/amd/display/amdgpu_dm/amdgpu_dm.c
patching file drivers/iommu/iommu.c
patching file drivers/nvmem/Kconfig
patching file drivers/perf/arm-cmn.c
patching file drivers/pinctrl/mediatek/mtk-eint.c
patching file drivers/pinctrl/mediatek/mtk-eint.h
patching file drivers/pinctrl/mediatek/pinctrl-mtk-common-v2.c
patching file drivers/pinctrl/mediatek/pinctrl-mtk-common.c
patching file drivers/pinctrl/mvebu/pinctrl-armada-37xx.c
patching file drivers/rtc/class.c
patching file drivers/rtc/lib.c
patching file drivers/thunderbolt/ctl.c
patching file drivers/tty/serial/jsm/jsm_tty.c
patching file drivers/usb/class/usbtmc.c
patching file drivers/usb/core/quirks.c
patching file drivers/usb/serial/pl2303.c
patching file drivers/usb/storage/unusual_uas.h
patching file drivers/usb/typec/ucsi/ucsi.h
patching file fs/bcachefs/dirent.c
patching file fs/bcachefs/dirent.h
patching file fs/bcachefs/errcode.h
patching file fs/bcachefs/fs.c
patching file fs/bcachefs/fsck.c
patching file fs/bcachefs/inode.c
patching file fs/bcachefs/namei.c
patching file fs/bcachefs/sb-errors_format.h
patching file fs/bcachefs/subvolume.c
patching file fs/coredump.c
patching file fs/pidfs.c
patching file include/acpi/actbl.h
patching file include/acpi/actypes.h
patching file include/acpi/platform/acgcc.h
patching file include/linux/coredump.h
patching file include/linux/iommu.h
patching file kernel/trace/trace.c
patching file net/sched/sch_hfsc.c
patching file tools/power/acpi/os_specific/service_layers/oslinuxtbl.c
patching file tools/power/acpi/tools/acpidump/apfiles.c
```

<br />




# Patch 3
```bash
clear;
KERNEL=6.15
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
KERNEL=6.15
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
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
KERNEL=6.15
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
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
KERNEL=6.15
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
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
KERNEL=6.15
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
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
KERNEL=6.15
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
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
KERNEL=6.15
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
KERNEL=6.15
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


```bash
clear;
KERNEL=6.15
WORKDIR=/mnt/data/kernel;
cd $WORKDIR;
rm -r linux-$KERNEL 2>/dev/null;
tar xf ./linux-$KERNEL.tar.xz;
cd ./linux-$KERNEL;
rm .config 2>/dev/null;


clear;
patch -p1 -R < ../patch-$KERNEL.1; make kernelversion;
patch -p1 -R < ../patch-$KERNEL.2; make kernelversion;
patch -p1 -R < ../patch-$KERNEL.3; make kernelversion;
patch -p1 -R < ../patch-$KERNEL.4; make kernelversion;
patch -p1 -R < ../patch-$KERNEL.5; make kernelversion;
patch -p1 -R < ../patch-$KERNEL.6; make kernelversion;
patch -p1 -R < ../patch-$KERNEL.7; make kernelversion;
patch -p1 -R < ../patch-$KERNEL.8; make kernelversion;
patch -p1 -R < ../patch-$KERNEL.9; make kernelversion;


clear;
patch -p1 -t < ../patch-$KERNEL.1; make kernelversion;
patch -p1 -t < ../patch-$KERNEL.2; make kernelversion;
patch -p1 -t < ../patch-$KERNEL.3; make kernelversion;
patch -p1 -t < ../patch-$KERNEL.4; make kernelversion;
patch -p1 -t < ../patch-$KERNEL.5; make kernelversion;
patch -p1 -t < ../patch-$KERNEL.6; make kernelversion;
patch -p1 -t < ../patch-$KERNEL.7; make kernelversion;
patch -p1 -t < ../patch-$KERNEL.8; make kernelversion;
patch -p1 -t < ../patch-$KERNEL.9; make kernelversion;



make defconfig;
make clean;
prlimit --as=21474836480 make -j$(( $(nproc) - 3 )) > compilation.log &;
tail -f compilation.log;

# Les options marquées [ * ] sont compilées directement dans le noyau.
# Les options marquées [ M ] seront compilées en modules.
# Les options désactivées ne sont pas incluses.

sudo make modules_install;
sudo make install;
sudo update-grub;
pkill gnome-session-b:
sudo reboot;
# sudo make modules install;
```
