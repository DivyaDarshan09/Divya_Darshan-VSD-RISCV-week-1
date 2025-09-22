# Day 2 - Timing Libs, Hierarchical vs Flat Synthesis & Efficient Loop Coding Styles

This document provides a summary of **Day 2** of **Week 1** in the 20-week RISC-V SoC Development Program.  
The focus of Day 2 is on **timing libraries, synthesis methodologies, and efficient flop coding styles**.

---

## Day 2 Repository Structure

```tree
Day-2/
├── 1-Introduction-to-Timing-Libs/
│   └── Readme.md
├── 2-Hierarchical-vs-Flat-Synthesis/
│   └── Readme.md
└── 3-Various-Flop-Coding-Styles-and-Optimizations/
    └── Readme.md
```
---

## Subdivisions

### [1️⃣ Introduction to Timing .libs](1-Introduction-to-Timing-Libs/Readme.md)
- Explored standard cell libraries, their **PVT variations**, and **equivalent Verilog models**.

### [2️⃣ Hierarchical vs Flat Synthesis](2-Hierarchical-vs-Flat-Synthesis/Readme.md)
- Learned different approaches to **synthesis** and their **trade-offs**.

### [3️⃣ Various Flop Coding Styles and Optimizations](3-Various-Flop-Coding-Styles-and-Optimizations/Readme.md)
- Understood efficient **coding techniques for flip-flops** and **optimization strategies**.

---
##  Tools Used

| **Tool**                   | **Purpose**                                  |
|-----------------------------|----------------------------------------------|
| Sky130 RTL Library          | Standard cell library for synthesis          |
| Verilog                     | RTL design and modeling                      |
| Yosys / Open-source Tools   | Logic synthesis and verification             |

---

## Learning Objectives

By the end of Day 2, I was able to:

- Understand the **structure and importance of timing libraries**.  
- Explore and analyze **PVT corners** and **equivalent Verilog models** of standard cells.  
- Compare **hierarchical vs flat synthesis approaches** and their trade-offs.  
- Learn **efficient flop coding styles** for better performance and area optimization.

---

## Wrap-Up  

From this exploration, I understood:  

- How **PVT variations** are captured in library file names.  
- How to view the **equivalent Verilog models** of cells.  
- That **different cell variants trade off area and performance**.  

This gave me a strong foundation on how timing libraries drive the **behavior, area, and delay characteristics** of standard cells.  

---