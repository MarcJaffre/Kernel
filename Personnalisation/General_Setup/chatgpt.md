--------------------------------------------------------------------------------------------------------
## I. Guide 
### A. Prompt
```
Quel est le meilleur paramètre pour un PC Ryzen 7 3700x sous Debian 12 :
```

#### 01. General Setup
```
- Compile also drivers which will not load : <Boolean>
- Compile the kernel with warnings as errors :  <Boolean>
- Compile test UAPI headers :  <Boolean>
- Local Version - apprend to kernel release: <String>
- Build ID Salt : <String>
- Kernel compression mode: <gzip, bzip, zstd, none>
- Default init path: <string>  
- Default Hostname: <string>
- System V IPC: <Boolean>
- POSIX Message queues : <Boolean>
- General notification queue : <Boolean>
- Enable process_vm_readv/writev_syscalls : <Boolean>
- uselib syscall (for libc5 and earlier)  : <Boolean>
- Auditing support : <Boolean>
- Preemption Model : <Boolean>
- Preemption behaviour defined on boot : <Boolean>
- Core Scheduling for SMT : <Boolean>
- CPU Isolation : <Boolean>
- Kernel .config support : <Boolean>
- Enable kernel headers throught /sys/kernel/kheaders.tar.xz : <Boolean>
- Kernel log buffer size : <Boolean>
- CPU Kernel log buffer size contribution : <Boolean>
- Printk indexing debugfs interface : <Boolean>
- Memory placement award NUMA scheduler : <Boolean>
- Checkpoint/restore support : <Boolean>
- Automatic process group scheduling : <number>
- Kernel -> user space relay support : <number>
- Initial Ram filesystem and RAM disk (initramfs/initrd) support : <string>
- Boot config support : <Boolean>
- Preserve cpio archive mtimes in intiramfs : <Boolean>
- Compiler optimisation level : <Boolean>
- Profiling support : <Boolean>
```



| Nom du paramètre                                  | Valeur     | Commentaire                                                                     |
| ------------------------------------------------- | ---------- | ------------------------------------------------------------------------------- |
| Compile also drivers which will not load          | false      | No need to compile unnecessary drivers                                          |
| Compile the kernel with warnings as errors        | true       | Ensure the kernel is compiled with strict error checking                        | 
| Compile test UAPI headers                         | false      | Not necessary for a standard kernel build                                       |
| Local Version - append to kernel release          | Debian     | Nappend the Debian version to the kernel release string)                        |
| Build ID Salt                                     | Debian     | Use a salt to ensure unique kernel builds                                       |
| Kernel compression mode                           | zstd       | Use the zstd compression algorithm for a good balance                           |
| Default init path                                 | /sbin/init | standard init path                                                              |
| Default Hostname                                  | Debian     | Set a default hostname, can be changed later                                    |
| System V IPC                                      | true       | Enable System V IPC for compatibility with older systems                        |
| POSIX Message queues                              | true       | Enable POSIX message queues for inter-process communication                     |
| General notification queue                        | true       | Enable the general notification queue for kernel events                         |
| Enable process_vm_readv/writev_syscalls           | true       | Enable process_vm_readv and writev syscalls for improved performance            |
| uselib syscall (for libc5 and earlier)            | false      | Not necessary for modern systems                                                |
| Auditing support                                  | true       | Enable auditing support for security and compliance                             |
| Preemption Model                                  | Voluntary  | Enable voluntary preemption for a balance between responsiveness and throughput |
| Preemption behaviour defined on boot              | true       | Allow preemption behaviour to be defined at boot time                           |
| Core Scheduling for SMT                           | true       | Enable core scheduling for SMT processors like Ryzen 7 3700x                    |
| CPU Isolation                                     | false      | Not necessary for a standard kernel build                                       |
| Kernel .config support                            | true       | Enable kernel .config support for custom kernel configurations                  |
| Enable kernel headers through .....               | true       | Enable kernel headers for development and debugging                             |
| Kernel log buffer size                            | 16         | Set a reasonable kernel log buffer size                                         |
| CPU Kernel log buffer size contribution           | true       | Enable CPU kernel log buffer size contribution                                  |
| Printk indexing debugfs interface                 | true       | Enable printk indexing debugfs interface for debugging                          |
| Memory placement award NUMA scheduler             | true       | Enable memory placement award NUMA scheduler for improved performance           |
| Checkpoint/restore support                        | false      | Not necessary for a standard kernel build                                       |
| Automatic process group scheduling                | 2          | Set a reasonable automatic process group scheduling value                       |
| Kernel -> user space relay support                | 2          | Set a reasonable kernel -> user space relay support value                       |
| Initial Ram filesystem and RAM disk ....          | initramfs  | Enable initramfs support for booting                                            |
| Boot config support                               | true       | Enable boot config support for custom boot configurations                       |
| Preserve cpio archive mtimes in initramfs         | true       | Preserve cpio archive mtimes in initramfs for consistency                       |
| Compiler optimisation level                       | 2          | Set a reasonable compiler optimisation level                                    |
| Profiling support                                 | true       | Enable profiling support for performance analysis                               |

<br />

#### 02. IRQ Sub-System
```
1. Supportsparse irq numbering : <>
2. Expose irq internals in debugfs : <>
```

<br />

#### 03 Timers subsystem
```
1. Timer tick handling : <>
2. Force user context tracking : <>
3. Old Idle dynticks config : <>
4. High Resolution Timer Support : <>
5. ClockSource Watchdog maximum allowable skew (in ms) :  <>
```



| Nom du paramètre                                  | Valeur     | Commentaire                                                                     |
| ------------------------------------------------- | ---------- | ------------------------------------------------------------------------------- |
| Timer tick handling                               | -----      | XXXXXXXXXXXXXXXXXX|
| Force user context tracking                       | -----      | XXXXXXXXXXXXXXXXXX|
| Old Idle dynticks config                          | -----      | XXXXXXXXXXXXXXXXXX|
| High Resolution Timer Suppor                      | -----      | XXXXXXXXXXXXXXXXXX|
| ClockSource Watchdog maximum allowable skew       | -----      | XXXXXXXXXXXXXXXXXX|

<br />


#### 04 BPF subsystem
```
1. Enable bpf() system call : <>
2. Enable BPF Just In Time compiler : <>
3. Permanently enable BPF JIT and remove BPF interpreter : <>
4. Disable unprivileged BPF by default : <>
5. Enable BPF LSM Instrumentation : <>
```

| Nom du paramètre                                       | Valeur     | Commentaire                                                                     |
| ------------------------------------------------------ | ---------- | ------------------------------------------------------------------------------- |
| Enable bpf() system call                               | -----      | XXXXXXXXXXXXXXXXXX|
| Enable BPF Just In Time compiler                       | -----      | XXXXXXXXXXXXXXXXXX|
| Old Idle dynticks config                               | -----      | XXXXXXXXXXXXXXXXXX|
| Permanently enable BPF JIT and remove BPF interpreter  | -----      | XXXXXXXXXXXXXXXXXX|
| Disable unprivileged BPF by default                    | -----      | XXXXXXXXXXXXXXXXXX|
| Enable BPF LSM Instrumentation                         | -----      | XXXXXXXXXXXXXXXXXX|

<br />

#### 05 CPU task time and stats accounting
```
1. Cputime accounting : <>
2. Fine granularity task level IRQ time accounting : <>
3. BSD Process Accounting : <>
4. Export task/process statistics through netlink : <>
5. Pressure stall information tracking : <>
```

| Nom du paramètre                                 | Valeur     | Commentaire                                                                     |
| ------------------------------------------------ | ---------- | ------------------------------------------------------------------------------- |
| Cputime accounting                               | -----      | XXXXXXXXXXXXXXXXXX|
| Fine granularity task level IRQ time accounting  | -----      | XXXXXXXXXXXXXXXXXX|
| BSD Process Accounting                           | -----      | XXXXXXXXXXXXXXXXXX|
| Export task/process statistics through netlink   | -----      | XXXXXXXXXXXXXXXXXX|
| Pressure stall information tracking              | -----      | XXXXXXXXXXXXXXXXXX|


<br />

#### 06 RCU Subsystem
```
1. Make expert-level adjustments to RCU : <>
2. Configuration Force selection of TASKS_RCU : <>
3. Force selection of Tasks Rude RCU : <>
4. Force selection of Tasks Trace RCU : <>
4A. Tree-based hierarchical RCU fanout value : <>
4B. Tree-based hierarchical RCU leaf-level fanout value : <>
5. Enable RCU priority boosting : <>
6. Offload RCU callback processing from boot-selected CPUs : <>
7. Tasks Trace RCU readers use memory barriers in user and idle : <>
8. RCU callback lazy invocation functionality (NEW) : <>
9. RCU callback-batch backup time check : <>
```

| Nom du paramètre                                              | Valeur     | Commentaire                                                                     |
| ------------------------------------------------------------- | ---------- | ------------------------------------------------------------------------------- |
| Make expert-level adjustments to RCU                          | -----      | XXXXXXXXXXXXXXXXXX|
| Configuration Force selection of TASKS_RCU                    | -----      | XXXXXXXXXXXXXXXXXX|
| Force selection of Tasks Rude RCU                             | -----      | XXXXXXXXXXXXXXXXXX|
| ------------------------------------------------------------- | ---------- | ------------------------------------------------------------------------------- |
| Force selection of Tasks Trace RCU                            | -----      | XXXXXXXXXXXXXXXXXX|
| Tree-based hierarchical RCU fanout value                      | -----      | XXXXXXXXXXXXXXXXXX|
| Tree-based hierarchical RCU leaf-level fanout value           | -----      | XXXXXXXXXXXXXXXXXX|
| ------------------------------------------------------------- | ---------- | ------------------------------------------------------------------------------- |
| Enable RCU priority boosting                                  | -----      | XXXXXXXXXXXXXXXXXX|
| Offload RCU callback processing from boot-selected CPUs       | -----      | XXXXXXXXXXXXXXXXXX|
| Tasks Trace RCU readers use memory barriers in user and idle  | -----      | XXXXXXXXXXXXXXXXXX|
| RCU callback lazy invocation functionality (NEW)              | -----      | XXXXXXXXXXXXXXXXXX|
| RCU callback-batch backup time check                          | -----      | XXXXXXXXXXXXXXXXXX|



<br />

#### 07 Scheduler features
```
```

<br />

#### 08 Control Group Support
```
```

<br />

#### 09 Namespaces Support
```
```

<br />

#### 10 Configure standard kernel features
```
```

<br />

#### 11 Kernel Performance Events And Counters
```
```

<br />

#### 12 Kexec and crash features









