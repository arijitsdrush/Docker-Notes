# Docker Basics

## Q. What is a Linux container and how it is different from VM?

**Answer:**  In a normal virtualized environment, one or more virtual machines run on top of a physical machine using a hypervisor like Xen, Hyper-V, etc.  _**Containers, on the other hand, run in userspace on top of operating systems kernel. It can be called as OS-level virtualization.**_  Each container will have its isolated user space and you can run multiple containers on a host, each having its own userspace. It means you can run different Linux systems (containers) on a single host. For example, you can run an RHEL and a SUSE container on an Ubuntu server. The Ubuntu Server can be a virtual machine or a physical host.

_**Note: you cannot run a windows container on a Linux host because there is no Linux Kernel support for Windows.**_

Containers are isolated in a host using the two Linux kernel features called namespaces and control groups.

**Namespaces:**  There are six namespaces in Linux

1.  **pid namespace**: Responsible for isolating the process (PID: Process ID).
2.  **net namespace**: It manages network interfaces (NET: Networking).
3.  **ipc namespace**: It manages access to IPC resources (IPC: InterProcess Communication).
4.  **mnt namespace**: Responsible for managing the filesystem mount points (MNT: Mount).
5.  **uts namespace**: Isolates kernel and version identifiers. (UTS: Unix Timesharing System).
6.  **user namespace**: Isolate UID/GID number spaces

Using these namespaces a container can have its own network interfaces, IP address, etc. Each container will have its own namespace and the processes running inside that namespace will not have any privileges outside its namespace.

**Control groups:**  The resources used by a container is managed by Linux control groups. You can decide on how much CPU and memory resource a container should use using Linux control groups.

## Q. What is Docker ?

**Answer:**  Docker is basically a container engine which uses the Linux Kernel features like namespaces and control groups to create containers on top of an operating system and automates application deployment on the container.

## Docker Components

Docker is composed of the following 4 primary components and 4 sub components

 1. Docker Engine or Docker Demon
 2. Docker Client
 3. Docker registries
 4. Docker objects
	   <ul>
	    <li>Docker Images</li>
	    <li>Docker Containers</li>
	    <li>Docker Volumes</li>
	    <li>Docker Networks</li>
	   </ul>

