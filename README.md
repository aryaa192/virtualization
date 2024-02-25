# What is virtualization?

Virtualization is a process that allows for more efficient utilization of physical computer hardware and is the **foundation of cloud computing**.

Virtualization uses s/w to create an abstraction layer over computer h/w that allows the h/w elements of a single computer - processors, memory, storage, and more to be divided into multiple virtual computers, commonly called **virtual machines(VMs)**. 

Each VM runs its own operating system (OS) and behaves like an independent computer, even though it is running on just a portion of the actual underlying computer h/w.

![alt text](assets/vm_arch.png)

# what is hypervisor?
The concept that we know virtualization is actually a technology whereas this hypervisor is its actual implementation.

**A hypervisor is a s/w or h/w component that enables the creation and management of virtual machines.**

### Types of hypervisors:

There are two primary types:

 Type 1 hypervisors (bare metal hypervisors):
![alt text](assets/hypervisor_t1_arch.png)


 - Run directly on the host without the need for un underlying operating system. 
 - offer superior performance and efficiency.
 - examples: KVM (Kernel-based VM), VMware vSphere Hypervisor(ESXi), MS Hyper-V Server, and Xen.

Type 2 hypervisors (hosted hypervisors):

![alt text](assets/hypervisor_t2_arch.png)
- Run on top of a host os in the user space.
- more user-friendly. 
- suitable for desktop or development env.
- examples: VMware workstation, VirtualBox, and Parallels Desktop.

### How hypervisors share or manages CPUs to across VMs running?

- sharing cpu or scheduling the threads to each core on the cpu is something that managed by host-os. The same idea applies to hypervisor. It does the same thing. 
- Allocating required CPU count to a VM doesn't mean that we have fixed those of pCPU to that VM.
- It works on top of that, We must know how threads get schedulled/queued to get tasks done by cores/processors.

![alt text](assets/cpu_management.png)

The above example explains how hypervisor helps to manage the tasks/threads requires from diff. VMs to be done.

As you can see, In VM3 it has a task/thread-9 where it's not yet allocated to any of the core cpu as there's no empty thread to pick it up. In this scenario it get into queue and once any task gets completed. It will be picked up and get done. This is how Core-Thread helps in multi-tasking concepts.

**Note: VMs Thread is not more than a process to a physical CPU. Same applies to all other resources. No matter what count or size we allocate to a VM it consumes only the required amount of resources.**

**Note: We can have as many as logical CPU in all total count of running VMs.**

**Note: We can't have more than the count of physical-CPU to any individual VM.**




