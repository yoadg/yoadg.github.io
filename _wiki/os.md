---
layout: page
title: Operating System
permalink: /os/
categories: 
  - compute
tags:
  - 
---

Every modern, general-purpose computer system needs an Operating System (OS) to run application programs. An operating system is system software that manages [computer hardware](/hardware), governs access to software resources and acts as an interface between computer hardware components and the user. It provides common services and functionalities that allow computer programs to run on the underlying machine. The main purpose of an operating system is to provide an environment in which a user can execute programs conveniently and efficiently. It manages the allocation of resources ([CPU](/hardware#central-processing-unit), [memory](/hardware#main-memory), [storage](/hardware#storage), etc.), ensuring that each process and application receives enough resources to function properly. It controls the policy of the system, by enforcing rules that regulate the behavior of different processes and security mechanisms to prevent misuse of the computer.

There are different types of operating systems, but in general most of them manage the following resources and services:
- **Processes** – The OS manages processes that are executed by the processor (CPU). The OS handles the creation, scheduling, blocking, suspension, resuming and termination of processes. It decides the order in which processes have access to the processor, and how much processing time each process has. It monitors running processes and keeps track of their statuses. It also provides mechanisms for synchronization and communication between processes.
- **Memory** – The OS manages the allocation and deallocation of main memory space that programs need for their execution. It keeps track of allocated and free memory space, and handles the protection of memory of one process from another.
- **Storage** – The OS manages a file system on secondary storage devices (disks). A file system is organized in a hierarchical structure of directories for efficient and easy navigation and usage. The OS handles the creation, retrieval, naming, deletion, sharing, and protection of files.
- **I/O Devices** – The OS manages all connected devices and their configuration. Its main function is to ensure that all the connected devices are correctly allocated and functioning. It designates a program responsible for every device known as the Input/Output controller. It decides which process gets access to a certain device and for how long. 
- **Jobs** – The OS determines the jobs/tasks that need to be processed first (based on their priorities) and ensures that these tasks are completed. It also keeps track of the time and resources used by various tasks and users.
- **Security** – The OS distinguishes between requests which should be allowed to be processed, and others which should not be processed. The authorization is based on user identity. 
- **Network** – The OS can share and access remote resources over the network. This includes everything from simple communication, to using networked file systems or even sharing another computer's graphics or sound hardware. 

![Operating system architecture](/assets/images/os.png)

*Operating system architecture*

## Kernel
The kernel is the core of the operating system and generally has complete control over everything in the system. It is the most important part of the operating system, the portion that is always resident in memory and servers as the primary interface between the hardware and the processes of a computer. A full kernel controls all hardware resources (e.g. I/O, memory) via [device drivers](#device-drivers), arbitrates conflicts between processes concerning such resources, and optimizes the utilization of common resources (e.g. CPU & cache usage, file systems, and network sockets). On most systems, the kernel is one of the first programs loaded on startup (after the bootloader). It handles the rest of startup as well as memory, peripherals, and input/output (I/O) requests from software, translating them into data-processing instructions for the CPU. When a user process makes a request to the kernel, it is called a system call.

The main purposes of the kernel are summarized below:
1. It determines which process is the next process on the CPU, when, and how long;
2. It monitors how much memory is being used to store what and where;
3. It serves as an interpreter between the hardware and processes;
4. It receives requests for service from the processes via system calls.

There are two modes for the code executed by the system on a CPU: kernel mode and user mode. The kernel runs in *kernel mode*. It has full access to the hardware, as well as access to all the free memory and the memory in use by the running programs. Applications operate in *user mode*. In this mode, direct access to the hardware is prohibited. Programs running in user mode are given an *address space*, visible only to themselves, which contains enough memory for them to do their job. 

## Device Drivers
A device driver is a software component that allows interaction with hardware devices. The driver provides an interface to peripheral hardware devices, enabling operating systems and other computer programs to access hardware functions without needing to know precise details about the hardware being used. Operating systems essentially dictate how every type of device should be controlled. The function of the device driver is then to translate these operating system mandated function calls into device specific calls. In theory a new device, which is controlled in a new manner, should function correctly if a suitable driver is available. This new driver ensures that the device appears to operate as usual from the operating system's point of view. Today, most operating systems include a library of plug-n-play drivers that allows peripheral hardware to connect automatically with an operating system. This approach also has the advantage of allowing programmers to write high-level application code without needing to know what hardware their code will run on.

## API
Application programs make use of the operating system by making requests for services through a well-defined Application Program Interface (API). The API enables applications to utilize OS and hardware functions without the need to know anything about the low-level OS or hardware state. From a programmer's point of view, an OS is defined mainly by the API that it provides. Native applications are tailored to use the OS on which the application intends to run. A consistent API allows the developer to write an application on one computer and have a high level of confidence that it will run on another computer with the same OS, usually regardless of the actual hardware components. 

At the top of the OS are *system calls*, which are the set of abstract operations that the kernel provides to application programs. When executed, a system call provides a controlled transition from user mode to kernel mode. Above the system calls there is a set of libraries that comes with the OS. Each library usually groups several related functions together. These are functions and subroutines which are useful for many programs.

## User Interface
Every computer that is to be operated by a human requires a User Interface (UI). The UI is usually referred to as a *shell* and is essential if human-computer interaction (HCI) is required. The UI requests services from the OS that will acquire data from input hardware devices, such as a keyboard and mouse and requests OS services to display prompts, status messages and such on output hardware devices, such as a video monitor (display) or printer. The UI allows the user to launch (run) application and system programs. 

The two most common forms of a UI have historically been:
- *Command-Line Interface (CLI)* – a terminal mode window that allows the user to type textual commands, which are executed by calling one or more of the underlying system programs or system calls.
- *Graphical User Interface (GUI)* – a visual desktop that allows the user to interact with the operating system by means of point-and-click operations.. 
