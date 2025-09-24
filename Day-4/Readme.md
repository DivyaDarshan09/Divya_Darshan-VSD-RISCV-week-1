# 📘 Day 4 – GLS, Blocking vs Non-Blocking & Synthesis-Simulation Mismatch  

Today’s focus was on **Gate-Level Simulation (GLS)**, **blocking vs non-blocking assignments**, and how these can lead to **synthesis–simulation mismatches**. The session was divided into three main parts, combining both theoretical understanding and practical lab experiments.  

---
```bash
Day4/
│── README.md # Main Day 4 report
│
├── GLS & Synthesis–Simulation Mismatch + Blocking/Non-Blocking Mismatch/
│ └── README.md 
│
├── Labs on GLS & Synthesis–Simulation Mismatch/
│ └── README.md 
│
└── Labs on Synthesis–Simulation Mismatch for Blocking Statements/
└── README.md 
``` 
---

##  Subdivisions  

1. [GLS & Synthesis–Simulation Mismatch + Blocking/Non-Blocking Mismatch](./1-GLS-Synthesis-Simulation-Mismatch-Blocking-NonBlocking/README.md)  
2. [Labs on GLS & Synthesis–Simulation Mismatch](./2-Labs-GLS-Synthesis-Simulation-Mismatch/README.md)  
3. [Labs on Synthesis–Simulation Mismatch for Blocking Statements](./3-Labs-Blocking-Simulation-Mismatch/README.md)  

---

##  Subdivision 1: GLS & Synthesis–Simulation Mismatch + Blocking/Non-Blocking Mismatch  

- **Gate-Level Simulation (GLS):**  
  GLS is performed after synthesis, using the **netlist** instead of RTL code. It helps verify whether the synthesized design behaves the same as the RTL simulation.  
  - GLS catches mismatches that arise due to coding style, synthesis tool optimizations, or blocking/non-blocking misusage.  
  - Timing effects can also be introduced during GLS.  

- **Synthesis–Simulation Mismatch:**  
  - Occurs when the RTL simulation and synthesized netlist behave differently.  
  - Reasons:  
    - Incorrect sensitivity lists  
    - Use of blocking (`=`) where non-blocking (`<=`) is expected  
    - Tool-specific synthesis optimizations  

- **Blocking vs Non-Blocking Mismatch:**  
  - **Blocking (`=`):** Executes immediately and can cause order-dependent behavior.  
  - **Non-blocking (`<=`):** Updates all values concurrently at the end of the time step, matching hardware behavior more accurately.  
  - Using blocking in sequential always blocks may work in simulation but fail after synthesis.  

---

## Subdivision 2: Labs on GLS & Synthesis–Simulation Mismatch  

In this part, we:  
- Ran **GLS** on synthesized netlists.  
- Observed how mismatches appear when the RTL uses improper coding style.  
- Analyzed the waveform differences between **RTL simulation** and **post-synthesis GLS**.  

This reinforced why GLS is an **essential verification step** before moving to layout.  

---

## Subdivision 3: Labs on Synthesis–Simulation Mismatch for Blocking Statements  

- We experimented with **blocking assignments (`=`)** inside sequential blocks.  
- Observed:  
  - Simulation gave results due to the ordered execution of statements.  
  - Post-synthesis GLS failed or gave incorrect results since hardware doesn’t follow the same ordered execution model.  
- Conclusion: Always use **non-blocking (`<=`)** in sequential always blocks to match real hardware behavior.  

---

##  What I Learned Today  

1. **GLS is mandatory** to catch mismatches between RTL and netlist.  
2. Synthesis-simulation mismatch often arises from **improper coding styles**.  
3. **Blocking vs non-blocking** plays a crucial role:  
   - Use `=` for combinational logic.  
   - Use `<=` for sequential logic.  
4. Labs demonstrated that **blocking assignments** may give expected results in RTL simulation but fail in GLS.  
5. Always verify with GLS before tapeout.  

---


✨ This completes **Day 4** of my learning journey.  

---