# Day 5 - Optimization in Synthesis

This document summarizes the learnings and practical labs carried out on **Day 5** of the 20-week RISC-V SoC Tapeout journey.  
The focus for today was **Optimization in Synthesis**, where we explored how different coding styles and constructs affect the synthesized design.

---

## Repository Structure for Day 5
```tree 
Day-5_Optimization_in_Synthesis/
│── README.md # Main Day 5 summary
│
├── If-Case_Constructs/
│ └── README.md
│
├── Incomplete_If-Case/
│ └── README.md
│
├── Incomplete_Overlapping_Case/
│ └── README.md
│
├── For-Loop_Generate/
│ └── README.md
│
└── Labs_For-Loop_Generate/
└── README.md
```

---

## Subtopics with Links

###  [If-Case Constructs](./1.If-Case_Constructs/Readme.md)
- Covers differences between **if** and **case** statements.  
- Observes how synthesis optimizes these constructs compared to simulation.

---

###  [Labs on Incomplete If-Case](./2.Incomplete_If-Case/Readme.md)
- Demonstrates issues with **incomplete if statements**.  
- Explains how synthesis can infer unintended **latches**.

---

###  [Labs on Incomplete Overlapping Case](./3.Incomplete_Overlapping_Case/Readme.md)
- Shows impact of **overlapping and incomplete cases**.  
- Highlights mismatches between RTL simulation and synthesized netlist.

---

###  [For-Loop and For-Generate](./4.For-Loop_Generate/Readme.md)
- Introduces **for-loops** in simulation vs synthesis.  
- Explains how **generate-for** expands into hardware logic.  

---

### [Labs on For-Loop and For-Generate](./5.Labs_For-Loop_Generate/Readme.md)
- Practical labs on **loop unrolling** and hardware replication.  
- Compares simulation outputs with synthesized results.  

---

##  Methodology
For each subdivision, the following steps were performed:
- ✅ Basic Simulation  
- ✅ RTL Simulation  
- ✅ Analysis of Results  
- ✅ Synthesis of Design  
- ✅ Observation of Mismatches/Optimizations  

---

## Key Takeaways
- Coding style strongly impacts the synthesized hardware.  
- Incomplete conditions can lead to **unwanted latches**.  
- Overlapping cases can cause **ambiguous logic** in synthesis.  
- Proper use of **for-generate** leads to efficient hardware mapping.  
- Always cross-check **simulation vs synthesis results** to ensure correctness.

---

✨ That’s all — these are the things we explored on **Day 5**.  
This file serves as the **main README** for Day 5, while each subdivision has its own detailed README with code, screenshots, and analysis.

---