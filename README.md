# Computer Architecture Simulator Suite

A C++ project implementing two fundamental computer architecture components:

1. **Cache Memory Simulator**
2. **5-Stage Pipelined RISC Processor Simulator**

This project was developed to explore memory hierarchy, cache organizations, instruction execution, pipelining, and hazard handling in modern processors.

---

## Overview

The repository contains:

### 1. Cache Simulator
A configurable cache simulator that supports different cache organizations and replacement policies.

### 2. Pipelined Processor Simulator
A custom 5-stage pipelined RISC processor simulator with support for instruction execution, memory access, branching, and hazard detection.

> Note: This is a custom RISC-style processor simulator and not a standard RISC-V implementation.

---

# Cache Simulator

## Features

### Cache Organizations
- Direct Mapped Cache
- Set Associative Cache
- Fully Associative Cache

### Replacement Policies
- LRU (Least Recently Used)
- LFU (Least Frequently Used)
- FIFO (First In First Out)
- Random Replacement

### Cache Miss Analysis
- Compulsory Misses
- Capacity Misses
- Conflict Misses

### Configurable Parameters
- Cache Size (1 KB – 64 KB)
- Block Size (4 – 128 Bytes)
- Associativity Level

---

## Memory Access Patterns

The simulator includes multiple memory generators:

| Generator | Description |
|------------|------------|
| memGen1 | Sequential access |
| memGen2 | Random access within 128KB |
| memGen3 | Random access over DRAM |
| memGen4 | Small working set |
| memGen5 | Medium working set |
| memGen6 | Strided access pattern |

---

## Sample Output

```text
Hits: 985632
Compulsory Misses: 128
Capacity Misses: 1024
Conflict Misses: 3216
```

---

# 5-Stage Pipelined Processor Simulator

## Pipeline Stages

### Instruction Fetch (IF)
Fetches instructions from memory.

### Instruction Decode (ID)
- Decodes opcode
- Reads register operands
- Generates control signals

### Execute (EX)
Performs ALU operations:

- ADD
- SUB
- MUL
- DIV
- MOD
- AND
- OR
- NOT
- MOV
- LSL
- LSR
- ASR

### Memory Access (MEM)
Handles:
- Load (LD)
- Store (ST)

### Write Back (WB)
Writes results back to the register file.

---

## Supported Instructions

### Arithmetic
- ADD
- SUB
- MUL
- DIV
- MOD

### Logical
- AND
- OR
- NOT

### Data Movement
- MOV
- LD
- ST

### Shift Operations
- LSL
- LSR
- ASR

### Control Flow
- BEQ
- BGT
- CALL
- RET

---

## Processor Features

### Register File
- 16 General Purpose Registers
- Stack Pointer (SP)
- Return Address Register (RA)

### Hazard Detection
- Data Hazard Detection
- Control Hazard Detection
- Pipeline Stalling
- Bubble Insertion

### Branch Handling
- Conditional Branches
- Unconditional Branches
- Function Calls
- Returns

---

## Pipeline Visualization

```text
+--------+--------+--------+--------+--------+
| FETCH  | DECODE | EXEC   | MEM    | WB     |
+--------+--------+--------+--------+--------+
```

The simulator can display instruction progression through each stage and show register values during execution.

# Project Structure

```text
.
├── CacheSimulator.cpp
├── Core.cpp
├── include/
│   ├── Core.h
│   ├── Memory.h
│   ├── PipelineRegister.h
│   └── Register.h
├── input/
├── output/
└── README.md
```

---

# Concepts Demonstrated
## Cache Memory
- Locality of Reference
- Cache Mapping Techniques
- Cache Replacement Policies
- Cache Miss Classification

## Processor Design
- Instruction Execution Cycle
- Pipeline Architecture
- Data Hazards
- Control Hazards
- Branch Processing
- Register File Design

## Computer Architecture
- Memory Hierarchy
- Instruction Set Design
- Processor Performance Analysis

---

# Future Improvements

- Implement standard RISC-V ISA support
- Data Forwarding
- Branch Prediction
- Multi-level Cache Hierarchy
- Cache Coherency Models
- Superscalar Execution
- Out-of-Order Execution

---

# Technologies Used

- C++
- Object-Oriented Design
- Computer Architecture Concepts
- Pipeline Simulation
- Cache Modeling

---

# Learning Outcomes

Through this project, the following concepts were explored:

- Cache Design and Optimization
- Pipeline Execution
- Hazard Detection and Resolution
- Memory Hierarchy
- Processor Simulation
- Performance Analysis
