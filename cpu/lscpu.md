# Command : lscpu

Listing all information about CPU

```bash
lscpu
lscpu -J # Json output
```

### Output information

**Architecture**
- Architecture
 - x86
    - uses complex instruction set computing ( CISC )
    - it supports more powerful operations and calculations
    - it used in desktop computers, servers
 - arm
    - uses reducted instruction set computing ( RISC )
    - it designed to be energy effiecient 
    - it used in smartphones, embeded devices
 - 32 bits vs 64 bits 
    - 32 bit register
        - cpu registers can store 32 bit addresses
        - so max ram can be 2 ^ 32 bits == 4 GB
    - 32 bit register
        - cpu registers can store 64 bit addresses
        - so max ram can be 2 ^ 64 bits == 18,446,744 GB
 
- CPU op-mode(s)
    - which size of instruction it supports ( 32 bit and 64 bit)
- Byte Order
    - sequence of byte arranged in memory in order to represent larger data value
    - two type 
        - little endian 
            - LSB is stored at lowest memory address
            - used in x86
            
        -  big endian 
            - MSB is stored at highest memory address
            - used in motorola 68k, ibm power pc
        - mixed endian 
            - depends on config
            - used in arm

- Address sizes
    - `39 bits physical and 48 bits virtual`
        - it indicates that cpu can access 2^39 bits ~ 512 GB of RAM directly
        - and 2^48 bits ~ 256 TB of virtual memory

**CPU Information**
- CPU(s)
    - number of logical cpus = number of sockets * number of cores per socket * number of threads per core 
- On-line CPU(s) list
    - 0-7 online cpus are online ( avilable to use )
- Thread(s) per core
    - Physical threads present in one core
    - Intel Hyper-Threading (HT)
    - AMD Simultaneous Multithreading (SMT):
- Core(s) per socket
    - Physical cores per socket
- Socket(s)
    - Socket referers to physical interface on motherboard
    - physical cpu present in system
- NUMA node(s)
    - Non uniform memory access
    - Numa node : group of processors that share thier local memory and have faster access to that memory
    - Each node has its own processor(s), memory, and sometimes I/O resources
- Vendor ID
    - CPU manufacturer
- CPU family
    - processor's microarchitecture generation
- Model
    - processor's model
- Model name
- Stepping
    - processor's revision / manufacturing iteration
- CPU MHz
    - CPU clock speed 
    - how many million cycle cpu can complete per second
    - one clock represent one electical pulse in processor
- CPU max MHz
    - max clock speed
- CPU min MHz
    - min clock speed
- BogoMIPS
    - cpu's performance measurement
    - measures loop iterations per second during boot
- Virtualization
    - hardware support for running virtual machines

**Cache Information**
- L1d cache
    - Data cache
- L1i cache
    - instruction cache
- L2 cache
    - Unified intermediate cache
- L3 cache
    - large shared cache

**NUMA Information**
- NUMA node0 CPU(s)
    - Logical CPUs assigned to this NUMA node 
And many more informations,,,