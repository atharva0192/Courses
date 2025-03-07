
# Introduction

- Computer is a machine that is programmed to perform a sequence of arithmetic and logical operations automatically

#### Distributed Computing
- In this type of computing different parts of computer program are run on two or more  computers that are connected over the internet
 ![[Pasted image 20250307010743.png]]

#### Cluster Computing
- In this type of parallel computing individual standalone computer work together as one integrated unit

#### Grid Computing
- combination of computer resources from multiple administrative domain that work together

#### Data Center Computing
- When computing exceed the resource there are two options :
	- Scale in (Vertical Scaling) - Increase the computation power per server
	- Scale out (Horizontal Scaling) - Increase the number of servers

### Cloud Computing
 - Cloud computing is a model for enabling convenient , on demand network access of multiple configurable computing resources that can be rapidly provided with minimum effort and service provider interaction.
#### Six Essential Characteristics:
1. **On-Demand Self-Service** – Users can provision computing resources automatically without human intervention.
2. **Broad Network Access** – Services are accessible over the internet from various devices (laptops, mobiles, tablets).
3. **Resource Pooling** – Multiple customers share resources dynamically allocated based on demand.
	1. **Rapid Elasticity** – Resources can scale up or down automatically as per demand.
4. **Measured Service** – Cloud usage is monitored, controlled, and billed based on resource consumption.
5. **Cost Associativity** - 1000 CPUs for 1 hr is same as 1CPU for 1000 hours

#### Virtualization and Its Types
- Decoupling from physical resources
- Types
	- Hardware
		- Emulation - QEMU
		- Para Virtualisation - Xen
		- Full Virtualisation - VMWare
	- Memory
		- RAM changes to virtual memory have mapping of virtual addresses to physical memory
	- Storage 
		- Abstracting logical storage from physical storage
	- Network
		- Virtualized network address with or within or across the network subnet

#### Service Models
1. Infrastructure as a Service
	1. Provide Computing Resources
	2. Amazon EC2
2. Platform as a Service
	1. Vendors Provide deployment environment
	2. Google App Engine
3. Software as a Service
	1. Provider controlled application over the internet
	2.  Google Docs


#### Deployment Models
1. Private Cloud
	1. Infrastructure managed by organization and third party
2. Community Cloud
	1. supports specific community
	2. Infrastructure shared by multiple organizations
3. Public Cloud
	1. Infrastructure made available to public
	2. Owned by organization selling cloud information
4. Hybrid Cloud
	1. Two or more cloud model

#### Cloud Distributed Storage
- Two approaches of scaling 
- CAP Theorem
	- web services cannot ensure all three of following properties at once
		- consistency
		- availability
		- partition tolerance
- Characteristics
	- Built on Distributed File System
	- Highly Available - Relaxed Consistency
	- Fault Tolerant - Replication
	- Eventually Consistent - Changes reflected in all replicas

#### Cloud Distributed Computation
- Functional Programming
	- Large problem broken into small problems
	- Each can be executed in complete isolation


# VMM

#### VM
- A virtual machine is a isolated environment that appears to be a whole computer, but actually has access to a portion of the physical resources
- Each VM appears to running on bare hardware
- Two Types
	- Process VM -  a virtual platform created for a process and then destroyed once completed
	- System VM - supports an OS and all its processes
- **Hypervisors**
	- A software that monitors and allocated resources to multiple VM instances
	- Allows several VM to run concurrently on same harware
	- Multiple Services sharing
	- Migration
	- Backward compatibility with original system
	- VMM runs in  Kernel Mode and Guest OS on user mode
- Classed of VM
	- Traditional VM
		- runs directly on hardware
		- Hardware - VMM - VMs
	- Hybrid
		- shares resources with host os
	- Hosted VM
		- runs under a host os
		- Hardware - Host OS - VMM - VMs

#### Virtualization Techniques
- System ISA Virtualization
- Instruction Set Interpretation
	- Interpret each instruction in C 
	- Very Slow
- Trap and Emulate
	- Not all architecture support it
	- Trap costs are high
- Binary Translation
	- Guest to Minimal set of host instruction and maintain a translation cache
	- Slow
- Hybrid Model

#### Code Portability
**Code portability** refers to the ability of software to be executed on different computing environments (hardware, operating systems, or architectures) **with minimal or no modification**
- Compile a High Level Language code for VM
- A portable code is produced and then distributed across the VMs on boot
- Then the VM loader converts ISA for guest into ISA of Host using binary translation
- This is called dynamic binary translation
- To improve performance these blocks are cached and reused

### VMM Virtualization of CPU and Memory
- CPU - Trap and Emulate
- Memory -
	- A **Guest OS** assumes it has direct access to physical memory and maintains its own page tables. However, in a virtualized environment, the **real memory is managed by the hypervisor**, which means:
	- The **guest’s page table** maps **virtual addresses → guest physical addresses**.
	- The **host (hypervisor) must map** guest physical addresses → actual **host physical addresses**.
	- The **Shadow Page Table (SPT)** is created by the hypervisor to track this **two-level mapping**, allowing the CPU to translate guest virtual addresses directly to host physical addresses.
	- VMM  maintains a SPT for each Guest OS and replicates any changes made my Guest into their SPT
	- Then this is used by MMU for dynamic address translation
- Manages the VMM to avoid performance degradation . Ex shutdown vm to avoid thrashing

### Working Of VMM
- Similar to how the OS multiplexes the processes on CPU
- VMM performs machine switch (like context switch) - run VM for a bit save context and then switch to other VM 

#### Problems of VMM
- Guest OS expects to have unrestricted access to hardware but VMM also runs in Kernel Mode having unrestricted access to the hardware . VM might interfere with the VMM thus costing security and isolation
#### Introduction of Rings
- WHY?
	- **Isolation & Security** – Ensures Guest OS cannot interfere with the Hypervisor.
	- **Controlled Hardware Access** – Prevents Guest OS from executing privileged instructions directly.
	- Ring de-privileging - VMMs forces OS and the apps to run at a privilege level > 0
	- Ring aliasing - guest OS forced to run at a privilege level other than that it was originally designed for.
	- Ring compression - paging and segmentation protect VMM code from being overwritten by guest OS and applications.
	- Guest system calls which cause transitions to/from privilege level 0 must be emulated by the VMM. 
	- Interrupt virtualization - in response to a physical interrupt, the VMM generates a virtual interrupt and delivers it later to the target guest OS which can mask interrupts.
#### Problems with Rings
- Some x86 instructions work differently based on the privileged mode
	- Sensitive information which change hardware state
		- popf 
	- How does OS realise its privileged mode
		- Some register in x86 reflects CPU privilege
		- For popf Eflags register are the indicator
- Why these issues ?
	- No hardware support in x86
	- Popek Goldberg Theorem
		- In order to built VMM efficiently via Trap and Emulate the sensitive instructions should be subset of privileged instruction
		- x86 does not satisfy this

#### Memory Virtualization
- GVA - GPA ->TLB(Translation Look Aside Buffer)
	- Each Guest OS thinks it has RAM access starting at 0
- GPA - HPA -> TLB
	- Guest RAM pages are distributed in Host Memory
- Shadow Paging : 
	- VMM creates two level mapping from GVA -> HPA
	- VMM tracks guest page table change and updates shadow page table
	- Handled by MMU

#### I/O Virtualization Techniques
- Emulation 
	- Guest OS operation traps to VMM then VMM does the rest
- Direct I/O
	- Assign slice of device



# Virtualization Techniques


## Hardware Assisted 
- Modern Technique for hardware support (VMX mode)
### Qemu Architecture

- Qemu -- Usespace Process
	- Works with binary translation if no hardware support
	- Set up VM as a userspace process
	- else it invokes KVM to switch to VMX
- KVM -- Kernel Module
- CPU with VMX 

- Libvirt
	- A set of tools to manage hyperisors including QEMU/KVM
	- Daemon that communicates with process
	- Exposes API for managing hypervisors and creating VM etc.
	- CLI tool - virsh
	- GUI - virt Manager
![[Pasted image 20250307040444.png]]

- QEMU is userspace process
- KVM exposes a dummy device at (/dev/kvm)
	- this allows QEMU to communicate with KVM using ioctl / open calls as very thing in linux is a file
- Allocates memory using mmap for Guest VM
- Create one thread for every vcpu so that it can run parallely
- Multiple FD to dummy device
	- One for QEMU
	- One for VM
	- One for VCPU
- Host os sees this as a regular multi threaded process
![[Pasted image 20250307041239.png]]
### QEMU operations
1. open dummy (/dev/kvm)
2. ioctl - Create VM in qemu fd
3. ioctl - Create VCPU in vm_fd
4. Each VCPU runs the following loop (infinite)
	1. ioctl(vcpu ,KVM_RUN)
		1. ioctl blocks thread , KVM switches to VMX mode runs guest VM
	2. on exit 
		1. Handle Exit - Return to Guest VM or QEMU
![[Pasted image 20250307041719.png]]
- VCPU has kvm_run structure with is shared between QEMU and KVM and stores information regarding VCPU thread parameters etc . Used to exchange information between userspace and kernelspace

#### VMX Mode
- Special Instruction to enter and exit VMX mode
- On entry and exit instructions , CPU switches context between host OS and Guest OS
	- Page tables and CPU registers etc
	- Managed by hardware
- Where?
	- VMCS (Virtual Machine Control Block)
	- Shared between both Host OS(root) and Guest OS(kernel)
	- One VMCS per VM
	- HOST CPU context , Guest CPU context , Guest entry / exit / execution control area , Exit Information is stored
	- This exit information is exchanged with QEMU via KVM_RUN struct because QEMU is in userspace
- Execution
	- Guest OS exits to KVM on certain instructions
		- KVM inspect the interrupts and perform action
	- No hardware access to GUEST
		- KVM can inject virtual interrupts to guest OS during VMX mode entry
	- Configured via VMCS
	- Mimics Trap and Emulate

## Full Virtualization