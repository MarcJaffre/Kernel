--------------------------------------------------------------------------------------------------------
## I. Guide 
### A. Prompt
```
Quel est le meilleur paramètre pour un PC Ryzen 7 3700x sous Debian 12 :
```

#### 01. Processor type and features
```
- 01. Symmetric multi-processing support : <boolean>
- 02. Support x2apic : <boolean>
- 03. Enable MSI and MSI-x delivery by posted interrupts (NEW) : <boolean>
- 04. Enable MPS table : <boolean>
- 05. x86 CPU resource control support : <boolean>
- 06. Flexible Return and Event Delivery (NEW) : <boolean>
- 07. Support for big SMP systems with more than 8 CPUs : ????

- 08. Support for extended (non-PC) x86 platforms : <boolean>
- 8A. Numascale NumaChip : <boolean>
- 8B. ScaleMP VSMP : <boolean>
- 8C. SGI Ultraviolet : <boolean>
- 8D. Goldfish (Virtual Platform) : <boolean>
- 8E. CE4100 TV platform : <boolean>
- 8F. Intel MID platform support : <boolean>
- 8G. Intel Quark platform support : <boolean>

- 09. Intel Low Power Subsystem Support : <boolean>
- 10. AMD ACPI2Platform devices support : <boolean>

- 11. Intel SoC IOSF Sideband support for SoC platforms : <boolean>
- 11A. Enable IOSF sideband access through debugfs : <boolean>

- 12. RDC R-321x SoC : <boolean>
- 13. Support non-standard 32-bit : <boolean>
- 14. SMP architectures : <boolean>
- 15. STA2X11 Companion Chip Support : <boolean>
- 16. Eurobraille/Iris poweroff module : <boolean>
- 17. Single-depth WCHAN output : <boolean>

- 18. Processor Family
- 18X. Generic-x86-64 [X]
- 18B. 486DX
- 18C. 586/K5/5x86/6x86/6x86MX
- 18D. Pentium-Classic
- 18E. Pentium-MMX
- 18F. Pentium-Pro
- 18G. Pentium-II/Celeron(pre-Coppermine)
- 18H. Pentium-III/Celeron(Coppermine)/Pentium-III Xeon
- 18I. Pentium M
- 18J. Pentium-4/Celeron(P4-based)/Pentium-4 M/older Xeon
- 18K. K6/K6-II/K6-III
- 18L. Athlon/Duron/K7
- 18M. Opteron/Athlon64/Hammer/K8
- 18N. Crusoe
- 18O. Efficeon
- 18P. Winchip-C6
- 18Q. Winchip-2/Winchip-2A/Winchip-3
- 18R. AMD Elan
- 18S. GeodeGX1
- 18T. Geode GX/LX
- 18U. CyrixIII/VIA-C3
- 18V. VIA C3-2 (Nehemiah)
- 18W. VIA C7
- 18X. Intel P4 / older Netburst based Xeon
- 18Y. Core 2/newer Xeon
- 18Z. Intel Atom

- 19. Generic x86 support : <boolean>
- 20. HPET Timer Support : <boolean>
- 21. Enable DMI scanning : <boolean>
- 22. Old AMD GART IOMMU support : <boolean>
- 23. Enable Maximum number of SMP Processors and NUMA Nodes : <boolean>
- 24. Maximum number of CPUs : <boolean>
- 25. Cluster scheduler support : <boolean>

- 26. Multi-core scheduler support : <boolean>
- 26A. CPU core priorities scheduler support : <boolean>

- 27. Local APIC support on uniprocessors : <boolean>
- 27A. IO-APIC support on uniprocessors : <boolean>

- 28. Reroute for broken boot IRQs : <boolean>

- 29. Machine Check / overheating reporting : <boolean>
- 29A. Support for deprecated /dev/mcelog character device
- 29B. Intel MCE features
- 29C. AMD MCE features
- 29D. Support for old Pentium 5 / WinChip machine checks

- 30. Machine check injector support
- 31. Legacy VM86 support
- 32. Enable support for 16-bit segments
- 33. Enable vsyscall emulation
- 34. IOPERM and IOPL Emulation
- 35. Toshiba Laptop support
- 36. Enable X86 board specific fixups for reboot
- 37. Late microcode loading (DANGEROUS)

- 38. Enforce late microcode loading minimal revision check
- 38A. /dev/cpu/*/msr - Model-specific register support
- 38B. /dev/cpu/*/cpuid - CPU information support
- 39. High Memory Support <OFF, 4GB, 64 GB>

- 40. Memory split
- 40A. 3G/1G user/kernel split
- 40B. 3G/1G user/kernel split (for full 1G low memory)
- 40C. 2G/2G user/kernel split
- 40D. 2G/2G user/kernel split (for full 2G low memory)
- 40E. 1G/3G user/kernel split

- 41. PAE (Physical Address Extension) Support
- 42. Enable 5-level page tables support
- 43. Enable statistic for Change Page Attribute
- 44. AMD Secure Memory Encryption (SME) support
- 45. NUMA Memory Allocation and Scheduler Support

- 45A. old style AMD Opteron NUMA detection
- 45B. ACPI NUMA detection
- 45C. NUMA emulation

- 46. Maximum NUMA Nodes (as a power of 2)
- 47. Enable sysfs memory/probe interface
- 48. Support non-standard NVDIMMs and ADR protected memory
- 49. Allocate 3rd-level pagetables from highmem
- 50. Check for low memory corruption
- 51. Set the default setting of memory_corruption_check
- 52. Math emulation

- 53. MTRR (Memory Type Range Register) support
- 53A. MTRR cleanup support
- 53B. MTRR cleanup enable value (0-1)
- 53C. MTRR cleanup spare reg num (0-7)
- 53D. x86 PAT support

- 54. User Mode Instruction Prevention
- 55. Indirect Branch Tracking
- 56. Memory Protection Keys
- 57. TSX enable mode
- 58. Software Guard extensions (SGX)
- 59. X86 userspace shadow stack (NEW)
- 60. Intel Trust Domain Extensions (TDX) host support

- 61. EFI runtime service support
- 61A. EFI stub support
- 61A_1. EFI handover protocol (DEPRECATED)
- 61A_2. EFI mixed-mode support
- 61B_1. Enable EFI fake memory map
- 61B_2. maximum allowable number of ranges in efi_fake_mem boot option
- 61C1. Export EFI runtime maps to sysfs

- 62. Timer frequency: <100,250,300,1000> MHz

- 63. Build a relocatable kernel
- 63A. Randomize the address of the kernel image (KASLR)

- 64. Alignment value to which kernel should be aligned
- 65. Randomize the kernel memory sections Physical memory mapping padding
- 66. Linear Address Masking support (NEW)
- 67. Disable the 32-bit vDSO (needed for glibc 2.3.3)

- 68. vsyscall table for legacy applications
- 68A. Emulate execution only 
- 68B. None

- 69. Built-in kernel command line
- 69A. Built-in kernel command string
- 69B. Built-in command line overrides boot loader arguments

- 70. Enable the LDT (local descriptor table)
- 71. Enforce strict size checking for sigaltstack
- 72. Kernel Live Patching
```
