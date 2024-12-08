---
layout: post
title: "Operating Systems I"
categories: operating_systems
tags: operating_systems foundation foundations
---

* TOC
{:toc}

Nowadays, OS have better support for networking. It used to be a nightmare and you had to write your own drivers in earlier days.



Portable Operating System Interface (POSIX)



## System Calls

Provides the services of an operating system to user programs



## Processes

If a program is made up of passive collection of instructions, then a process is the actual execution of those instructions

PID, process ID

pthreads, POSIX threads

Different default init system exists, such as:
sinit
systemd

PID 1 is usually what starts and shuts down the system



### Inter-Process Communication (IPC)

signal

kill

"The collection of signals that are currently blocked is called the signal mask. Each process has its own signal mask."

"A signal handler is special function (defined in the software program code and registered with the kernel) that gets executed when a particular signal arrives. This causes the interruption of current executing process and all the current registers are also saved."



## File Systems

block-oriented file system



File descriptors are simply integers that uniquely identifies an open file or a communication channel (like a pipe) for a specific process

It's like a label used by a process to perform some operations (like read, write) on a file

- 0 for standard input (stdin)
- 1 for standard output (stdout)
- 2 for standard error (stderr)



Files have metadata



## Memory Management



## Virtual Memory



## Scheduling

Implemented so that computer resources are balanced (load balancing), allows multiple users to share system resources, achieve a target quality of service 



## Threads

thundering herd problem



### Multithreading

Benefits of multithreading operations:
improved throughput
full use of processors
entire applications will not block because of one request
minimized system resource usage because threads now require less overhead to create, maintain, and manage than a traditional process

thread pool, a software design pattern (for concurrency)
also known as replicated workers or worker-crew model



A general rule to calculate total number of threads a CPU can handle:

A CPU without SMT (Simultaneous Multithreading, such as Hyperthreading) = 1 thread (1 core * 1 thread per core)

A CPU with SMT = 2 threads (1 core * 2 threads per core)



## Input/Output, I/O

Blocking IO means that a thread cannot do anything more until the IO is fully received 
This means that you will need to wait for every IO request or open a thread per request

Non-blocking IO means an IO request is queued immediately and the function returns
The actual IO is then processed at a later time by the kernel
This means you can open multiple requests but the data will not be available until later
Checking whether the data is available is probably the most complicated part

In majority of applications, IO blocking isn't an issue
When dealing with this, you're dealing with performance



### Polling (vs Interrupts)



## Deadlock

Semaphore is a synchronization primitive using acquire and release functions. A semaphore manages an internal counter which is decremented by each acquire call and incremented by each release call. The counter can never go below zero. When release finds that it is zero, it blocks and wait until a thread calls release. It defaults to 1.



## Security



## Concurrency



## Interesting

### [TempleOS](https://www.templeos.org)

Terry A. Davis

"TempleOS is a 64 bit, non-preemptive multi-tasking, multi-cored, public domain, open source, ring-0-only, single address space, non-networked, PC operating system for recreational programming."


