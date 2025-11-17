# 🖥️ From Bits to Systems — CS:APP Study Journey  
“Abstraction is powerful — but understanding what lies beneath is transformative.” — CS:APP

This repository documents my progress through **_Computer Systems: A Programmer’s Perspective_ (CS:APP)** as part of my TYCS self-study curriculum.  
In this phase, I’m diving below high-level programming and exploring how data, instructions, and processes actually behave at the machine and system level.

Each chapter includes notes, code experiments, exercise solutions, and conceptual summaries.

---

## 🧭 Overview  
CS:APP provides a programmer-focused understanding of how computer systems execute programs, manage data, handle memory, and interact with hardware.

This journey builds intuition across the entire systems stack — starting from how bits represent information, all the way to linking, memory, processes, and low-level performance behavior.

You start with data representations, then build an understanding of:

- The machine-level model of program execution  
- Assembly and control flow  
- The memory hierarchy  
- Linking, loading, and runtime behavior  
- Processes, signals, and system-level I/O  

---

## 📚 Chapters & Key Achievements  

| Chapter | Focus | Highlights |
|--------|--------|------------|
| **1** | **Bits, Bytes, and Data Representation** | Understood how integers, floats, pointers, and machine words are represented; practiced bit-level manipulation and debugging unexpected behavior caused by overflow |
| **2** | **Machine-Level Programming** | Learned how C maps to assembly (x86-64); analyzed control flow, procedure calls, stack frames, and memory addressing; wrote small programs directly in assembly to internalize the execution model |
| **3** | **Program Optimization** | Explored how compilers optimize code, how to write cache-friendly loops, unroll operations, reduce branch mispredictions, and reason about performance at the instruction level |
| **4** | **The Memory Hierarchy** | Studied caches, locality, and the performance cost of memory access; wrote experiments to measure cache behavior and see real-world latency differences |
| **5** | **Linking** | Explored object files, symbols, the linker, relocations, static vs dynamic linking; inspected binaries using `objdump` and built small examples showing linking errors and symbol resolution |
| **6** | **Exceptional Control Flow** | Learned how processes, signals, traps, and system events work; implemented small signal-handling programs and process-control experiments |
| **7+** | **(Upcoming)** Virtual memory, dynamic allocation, system-level I/O, concurrency |

---

## 🧩 What This Phase Builds  

By working through CS:APP, I’m building a deep understanding of how programs truly run:

- How data is processed at bit-level precision  
- How the CPU executes instructions and manages control flow  
- How the call stack works under the hood  
- How memory and caches shape performance  
- How binaries are compiled, linked, loaded, and executed  
- How processes interact with the OS and with each other  

All of this forms the foundation for writing safer, faster, and more systems-aware code.

This work also sets the stage for the next phase:

- Implementing malloc/free  
- Exploring virtual memory  
- Writing concurrent programs  
- Understanding low-level I/O  
- Building real-world systems tools and performance analyzers  

---

Thanks for following along — more chapters coming soon.
