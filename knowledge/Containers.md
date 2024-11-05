---
title: Containers
---
A **container** cannot be defined as a [virtual machine](Virtualization.md) but as an isolated group of processes running on a single host that corresponds to a complete application, including its configuration and dependencies.

This application is packaged in a precisely defined and reusable format. Unlike a usual VM on VMware Workstation, however, a container does not contain its operating system or kernel. It is, therefore, not a virtualized operating system.

For this reason, containers are significantly slimmer than conventional virtual machines. Precisely because they are not real virtual machines, they are also referred to as application virtualization in this context.

![VM vs Containers](/knowledge/assets/containers-vs-virtual-machines.jpg "VM vs Containers")

| **Virtual Machine**                                                | **Container**                                                                                              |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- |
| Contain applications and the complete operating system             | **Contain applications** and only the necessary operating system components such as libraries and binaries |
| A hypervisor such as VMware ESXi provides virtualization           | The operating system with the container engine provides its own virtualization                             |
| Multiple VMs run in isolation from each other on a physical server | Several containers run isolated from each other on one operating system                                    |

An image of the file system forms the basis of each container. We can choose whether to use an image that has already been created or to create one ourselves. Containers are also characterized by outstanding scalability. Improved scalability is ideally suited to the requirements of the now highly dynamic IT infrastructure in companies. 

## Docker

#Docker is #opensource source software that can isolate applications in containers, similar to operating system virtualization. This approach significantly **simplifies the deployment of applications**.

The application data stored in the containers can be transported and installed easily. The use of containers ensures that computer resources are strictly separated from each other. Docker stores programs together with their dependencies in images. These form the basis for virtualized containers that can run on almost any operating system.

This makes **applications portable and uncomplicated**, whether during development or when scaling SaaS clusters.

- Website : https://www.docker.com/get-started
- Docker Engine : https://docs.docker.com/engine/

## Vagrant

Vagrant is a tool that can create, configure and manage virtual machines or virtual machine environments. The VMs are not created and configured manually but are described in code in a Vagrantfile. To better structure the program code, the Vagrant file can include additional code files. The code can then be processed using the Vagrant CLI.

In this way, we can create, provision, and start our own VMs. Moreover, if the VMs are no longer needed, they can be destroyed just as quickly and easily. Out of the box, Vagrant offers providers for VMware and Docker.

- Website : https://www.vagrantup.com/

