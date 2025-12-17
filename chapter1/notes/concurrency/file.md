# Concurrency in Computer Systems

Concurrency arises when a system supports the execution of multiple activities at the same time. Building on the **process** abstraction, modern computer systems provide several forms of concurrency at different levels of abstraction.

---

## Thread-Level Concurrency

**Thread-level concurrency** refers to the execution of multiple control flows at the same time. Using threads, a single process can have multiple flows of control executing concurrently.

Historically, concurrency was achieved on **uniprocessor systems** by rapidly switching among processes, giving the illusion that multiple programs were executing simultaneously. This technique enabled time-sharing systems, allowing multiple users and tasks to make progress concurrently.

With the advent of **multiprocessor systems**, true parallel execution became possible. A multiprocessor system consists of multiple cpu cores grouped in a single chipset.

### Hyperthreading
**Hyperthreading**, also known as **simultaneous multithreading (SMT)**, allows a single core to execute multiple threads.

This is achieved by giving each core more than one set (typically two) of hardware state, such as the program counter, the register file and an L1 cache. An L2 cache is shared by the threads within the same core, while an L3 cache is shared among all cores.

For example, in an Intel Core i7 processor, each of the four cores can execute two threads, allowing up to eight threads to run at the same time.
---

## Instruction-Level Parallelism

At a lower level, processors can execute multiple instructions at the same time, a property known as **instruction-level parallelism (ILP)**.

- Early processors required multiple clock cycles to execute a single instruction.
- Modern processors can sustain execution rates of multiple instructions per clock cycle.

### Pipelining
This is possible because instruction execution is divided into multiple stages, forming a **pipeline**.
- Different stages operate in parallel on different instructions.
- This organization can achieve close to one completed instruction per clock cycle.

### Superscalar processors
Processors that can sustain execution rates greater than one instruction per cycle are known as **superscalar processors**.
- Most modern processors support superscalar execution.
- Programs that expose more instruction-level parallelism can achieve higher performance.

---

## Single-Instruction, Multiple-Data (SIMD) Parallelism

At the lowest level, many processors support **single-instruction, multiple-data (SIMD)** parallelism.

- A single instruction operates on multiple data elements in parallel.
- For example, one instruction may add multiple pairs of floating-point numbers simultaneously.

SIMD parallelism is commonly used to accelerate applications that process image, audio, and video data. Some compilers can automatically exploit SIMD parallelism, but it is often accessed explicitly using special vector data types.

---
