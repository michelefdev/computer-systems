# Operating System Abstractions — Processes, Virtual Memory, Files

The operating system provides a set of abstractions that allow application programs to use the hardware safely and efficiently. Three of the most important abstractions are **processes**, **virtual memory**, and **files**.

---

## 1. Processes

A **process** is the operating system’s abstraction for a running program. Each process provides a program with the illusion that it has exclusive use of the processor, main memory, and I/O devices.

The operating system keeps track of all the state information that a process needs in order to run. This state, known as the **process context**, includes information such as the current values of the program counter, the register file, and the contents of main memory.

### Context switching
- The operating system implements multitasking by performing **context switches**.
- During a context switch, the kernel saves the context of the current process, selects another runnable process, and restores the saved context of the new process.

### Threads
- A process can consist of **multiple threads** of execution.

---

## 2. Virtual Memory and Address Space

**Virtual memory** is an abstraction that provides each process with the illusion that it has exclusive use of main memory. Each process has the same uniform view of memory, known as its **virtual address space**.

Virtual memory allows the operating system to efficiently use main memory and to protect the memory of one process from access by another process.

### Typical layout (Linux/x86-64 style)

```
Low addresses
  [ Read-only code and data ]
  [ Read/write data ]
  [ Heap ]          ← grows upward (e.g., via malloc)
  [ Memory-mapped region ]
  [ Stack ]         ← grows downward on procedure calls
High addresses
  [ Kernel virtual memory ] (inaccessible to user programs)
```

---

## 3. Files

A **file** is a sequence of bytes, nothing more and nothing less.

All I/O devices are modeled as files, and all input and output in the system is performed by reading from and writing to files.

---
