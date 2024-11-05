---
title: Virtualization
---
**Virtualization** is an abstraction of physical computing resources. Both hardware and software components can be abstracted. A computer component created as part of virtualization is referred to as a virtual or logical component and can be used precisely as its physical counterpart.

The main advantage of virtualization is the abstraction layer between the physical resource and the virtual image.

This is the basis of various cloud services, which are becoming increasingly important in everyday business. Virtualization must be distinguished from the concepts of simulation and emulation.

- Hardware virtualization
- Application virtualization
- Storage virtualization
- Data virtualization
- Network virtualization

## Virtual Machines

A **virtual machine (VM)** is a virtual operating system that runs on a host system (an actual physical computer system).

Several VMs isolated from each other can be operated in parallel. The physical hardware resources of the host system are allocated via hypervisors. This is a sealed-off, virtualized environment with which several guest systems can be operated, independent of the operating system, in parallel, on one physical computer. The VMs act independently of each other and do not influence each other.

A hypervisor manages the hardware resources, and from the virtual machine's point of view, allocated computing power, RAM, hard disk capacity, and network connections are exclusively available.
### Benefits of VM : 
1. Applications and services of a VM do not interfere with each other
2. Complete independence of the guest system from the host system's operating system and the underlying physical hardware
3. VMs can be moved or cloned to other systems by simple copying
4. Hardware resources can be dynamically allocated via the hypervisor
5. Better and more efficient utilization of existing hardware resources
6. Shorter provisioning times for systems and applications
7. Simplified management of virtual systems
8. Higher availability of VMs due to independence from physical resources

## Virtualization Software Products

- VMware
- VirtualBox
- HyperV

