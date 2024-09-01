---------------------------------------------------------------------------------
# <p align='center'> Kexec and crash features </p>
---------------------------------------------------------------------------------
### A. Présentation

<br />

### B. Configuration
#### 1. Enable kexec system call


<br />

#### 2. Enable kexec file based system call


<br />

#### 3. Verify kernel signature during kexec_file_load() syscall


<br />

##### A. Require a valid signature in kexec_file_load() syscall


<br />

##### B. Enable Image signature verification support (ARM)

<br />

##### C. Enable bzlmage signature verification support


<br />

#### 4. kexec jump


<br />

#### 5. kernel crash dumps

##### A. Update the crash elfcorehdr on system configuration changes (NEW)
##### B. Specify the maximum number of memory regions for the elfcorehdr (NEW)



