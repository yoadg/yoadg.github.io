---
layout: page
title: Basic Computer Architecture
permalink: /hardware/
categories: 
  - compute
tags:
  - hardware
---
A computer is a digital electronic machine that can be programmed to carry out sequences of arithmetic or logical operations, known as programs. Computers control a wide range of devices, such as servers, personal computers, mobile phones, Smart TVs, Wearable and IoT devices. These devices have different architectures but the basic compute hardware shares some common components. The *von Neumann* computer architecture that was described in 1945 (also known as the *stored-program architecture*), includes the following components that are still valid in modern computers:
- A processing unit with both an arithmetic logic unit and processor registers
- A control unit that includes an instruction register and a program counter
- (Main) memory that stores data and instructions
- External mass (secondary) storage
- Input and output mechanisms

![Basic computer architecture](/assets/images/hardware.png)

*Basic computer architecture*

## Central Processing Unit
At the heart of any computer is the CPU (also called a central processor, main processor or just processor), the hardware unit that executes the computer programs. If we want to humanize our computer, it would resemble the “brain” of the system. The CPU is basically composed of the following components:
- **Control Unit** (CU): The main component that directs the operation of the processor.
- **Arithmetic Logic Unit** (ALU): A combinational digital circuit that performs arithmetic and bitwise operations on integer binary numbers.
- **Processor Registers**: A temporary storage area that holds instructions, storage addresses and other needed data for program execution.

In a modern microprocessor all these components are implemented on a single, integrated circuit (“chip”).

The CPU It is capable of running computer programs that are written in machine code language (opcodes), consisting of machine language instructions. Each instruction is a very specific task, such as a load, a store, a jump, or an arithmetic/logic operation on one or more units of data in the CPU's registers or memory. In order to execute a program, the CPU interacts with the main memory in a series of steps known as the *Instruction (or Machine) Cycle*:
1. **Fetch** – In the first step, the CPU retrieves an instruction from the memory. The instruction's location (address) in program memory is determined by the *Program Counter* (PC), which stores a number that identifies the address of the next instruction to be fetched. Then the control unit sends out a signal to copy the data from that address to the *Instruction Register* (IR). After an instruction is fetched, the PC is incremented by the length of the instruction so that it will contain the address of the next instruction in the sequence.
2. **Decode** – Once an instruction is fetched and stored in the IR, the control unit needs to figure out how to use the instruction. During this stage, the encoded instruction presented in the instruction register is interpreted by the instrcution decoder, and then it is converted into signals, as defined by the CPU's instruction set architecture (ISA). 
3. **Execute** – In the final step, the control unit takes the decoded information and passes it as electrical signals to the relevant parts of the CPU. Depending on the CPU architecture, this may consist of a single action or a sequence of actions. The action is then completed, typically in response to a clock pulse. Very often the results are written to an internal CPU register for quick access by subsequent instructions. In other cases results may be stored in the slower, but less expensive and higher capacity main memory, or sent to an output device.

The overall execution of a specific program with its context (PC, registers, address space etc.) is called a *process*. The CPU is capable of running a single process at any given time. In order to achieve concurrency, the processor performs effective *context switching* from one process to another in negligible time that gives an illusion of simultaneous execution. Modern CPUs are *multi-core* processors, meaning that a single physical processor chip actually has multiple processing units in it (today between 2 and 16), called cores. Multi-core CPUs are capable of running more than one process at the same time, increasing the overall speed for programs that support multithreading or other parallel computing techniques.

## Main Memory
Primary storage (also known as main memory, internal memory, or prime memory), often referred to simply as memory, is the only one directly accessible to the CPU. *Random Access Memory* (RAM) is a form of computer memory that can be read and changed in any order, typically used to store working data and machine code. It is used as the computer's short-term, temporary working memory, where the data that the processor is currently using is stored for quick access. RAM keeps data easily accessible so the processor can quickly find it without having to go into long-term storage to complete immediate processing tasks. It is a volatile storage, losing its contents when the system loses power or shuts down. Thus, any information stored in RAM that should be retained, must be written to some form of permanent storage before the system powers off. 

Each location in the memory space has a unique, sequential address. The address of a memory location is used to specify (and select) that location. The memory space is also known as the address space. The address space is the array of all addressable memory locations. Usually more than one bit of storage is accessed by the same address, and RAM devices often have multiple data lines and are said to be "8-bit" or "16-bit", etc. devices. When a computer is called a "32-bit" computer, this means that the data bus is 32 bits in size, and reads & writes to/from memory are normally done in groups of 32 bits. 

The two widely used forms of modern RAM are *static RAM* (SRAM) and *dynamic RAM* (DRAM). SRAM is the fastest form of RAM available, requires little external support circuitry, and has relatively low power consumption. SRAM can hold data without needing to be constantly refreshed, unlike DRAM. The drawbacks of SRAM are that its capacity is considerably less than DRAM, while being much more expensive. 

## Cache
Computer memory has a hierarchy based upon its operational speed. The CPU cache stands at the top of this hierarchy, being the fastest. This is a hardware cache used by the CPU to reduce the average cost (time or energy) to access data from the main memory. This cache is a smaller, faster memory, located closer to a processor core, which stores copies of the data from frequently used main memory locations. Most CPUs have a hierarchy of multiple cache levels (L1, L2, often L3, and rarely even L4), with different instruction-specific and data-specific caches at level 1. The cache memory is typically implemented with SRAM. 

## Input/Output
The address space of the processor can contain devices other than memory. These are input/output devices (I/O devices, also known as peripherals) and are used by the processor to communicate with the external world. There are three types of peripherals:
1. **Input peripherals**: Devices that enable user input, from the outside world to the computer. Examples: keyboard, mouse, touch pad, camera, microphone, scanner, etc.
2. **Output peripherals**: Devices that enable information output, from the computer to the outside world. Examples: monitor, speakers, printer, etc.
3. **Input/Output peripherals**: Devices that enable both input and output (between the computer and the outside world). Examples: touch screen, network card, hard disk, disk on key, etc.

Data transfer to and from the peripherals may be done in any of the three possible ways:
1. **Programmed I/O** – The processor accepts or delivers data as a result of the I/O instructions that are written in the computer program.
2. **Interrupt-initiated I/O** – External events control the processor by requesting the current program be suspended and the external event be serviced. An external device will interrupt the processor (assert an interrupt control line into the processor), at which time the processor will suspend the current task (program) and begin executing an interrupt service routine. The service of an interrupt may involve transferring data from input to memory, or from memory to output. 
3. **Direct memory access (DMA)** – Data can be transferred from I/O devices to memory directly using the memory buses, without the continuous involvement of the processor. DMA is used in high-speed systems, where the rate of data transfer is important. 

## Storage
Secondary storage (also known as external memory, auxiliary storage, disk or just storage) differs from primary storage (main memory) in that it is not directly accessible by the CPU. The computer usually uses its input/output channels to access secondary storage and transfer the desired data to/from primary storage. Secondary storage is non-volatile (retaining data when its power is shut off). Modern computer systems typically have two orders of magnitude more secondary storage than primary storage because secondary storage is less expensive. Secondary storage can hold and handle significantly larger sizes of data, and keeps it inactive until it’s needed again.

Although a computer can run with no storage device, it would only be able to view information, unless it was connected to another computer that had storage capabilities. Storage devices include a broad range of different magnetic, optical, flash, and virtual drives. In modern computers, most storage devices are either Hard Disk Drives (HDDs), based on magnetic palettes, or Solid-State Drives (SSDs), which are typically based on flash memory. The access time per byte for HDDs or SSDs is typically measured in milliseconds, while the access time per byte for primary storage is measured in nanoseconds. Input/output Operations per Second (IOPS) is an input/output performance measurement used to characterize computer storage devices. Generally HDDs have an IOPS range of 75-400, while SSDs have IOPS from 20,000 to 100,000.

## Read Only Memory
ROM is a type of non-volatile memory used in computers, requiring no power to retain their contents. The primary purpose of ROM within a system is to hold the code (and sometimes data) that needs to be present at power-up. Such software is generally known as *firmware* and contains software to initialize the computer by placing I/O devices into a known state. It may contain either a bootloader program to load an [operating system](/os) off disk or network or, in the case of an embedded system, it may contain the application itself. Many microcontrollers contain on-chip ROM, thereby reducing component count and simplifying system design.

On a PC, the boot ROM is called the Basic Input/Output System (BIOS), or the newer Unified Extensible Firmware Interface (UEFI). When the processor starts, it begins executing instructions it finds in the BIOS. The BIOS instructions do things like test the hardware in the machine, and then it goes to the hard disk to fetch the boot sector. This boot sector is another small program, and the BIOS stores it in RAM after reading it off the disk. The processor then begins executing the boot sector's instructions from RAM. The boot sector program will tell the processor to fetch something else from the hard disk into RAM, which the processor then executes, and so on. This is how the processor loads and executes the operating system's [kernel](/os#kernel).

## Graphic Processing Unit
A GPU is a specialized electronic circuit designed to manipulate and alter memory to accelerate the creation of images in a frame buffer intended for output to a display device. The GPU can be integrated into the motherboard or be found in the daughterboard of a graphics card. Designed for parallel processing, GPUs are used in a wide range of applications, including graphics and video rendering. Although they’re best known for their capabilities in gaming (especially for 3D graphics), GPUs are becoming more popular for use in creative production and artificial intelligence (AI), especially in the domain of image processing. A GPU complements the CPU architecture by allowing repetitive calculations within an application to be run in parallel while the main program continues to run on the CPU. The CPU can be thought of as the taskmaster of the entire system, coordinating a wide range of general-purpose computing tasks, with the GPU performing a narrower range of more specialized tasks (usually mathematical). The GPU is made up of many smaller and more specialized cores, which can complete more work in the same amount of time as compared to a CPU.

