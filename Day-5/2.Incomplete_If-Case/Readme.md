# 2. Labs on Incomplete If-Case

This document explains the second subdivision of **Day 5 - Optimization in Synthesis**.  
In this section, we performed hands-on labs to understand how incomplete if statements behave during simulation and synthesis.

---

## What I Learned
- Writing incomplete if statements causes the synthesizer to infer latches, which is not good practice.  
- RTL simulation alone may not reveal hardware issues — synthesis analysis is also important.  
- Always complete the if-else structure to ensure predictable and optimized hardware.  
- Good coding style directly impacts the quality of synthesized circuits.  

---
## Files Used
1. `incomp_if.v`  
2. `incomp_if2.v`  

These files contain examples of **incomplete if statements**.

---

## Concept: Incomplete If Statement
- An **incomplete if** occurs when an `else` branch is missing.  
- In synthesis, this results in **inferred latches** because the output retains its previous value when no condition is true.  
- This is considered a **bad coding style** and should be avoided.

---

## 1. 1st Example (incomp_if.v)


### Code Analysis

- The Verilog source code clearly shows missing else conditions.  

![verilog code (incomp_if.v)](.Screenshots/code_incomp_if.jpg)

---

### RTL Simulation

- We first ran an RTL simulation to observe the output behavior of the incomplete if statements.  

![ RTL simulation result](.Screenshots/rtl_incomp_if.jpg)

- In this case , if `i0` is high, the output `y` exactly follows the `i1`.
- But if `i0` goes low, the output is confused, what to follow.
- So it latched into the previous value of `y` until `i0` becomes 1. 

---

### Synthesis printing statistics and Graphical View 

- After synthesis, we observed that the synthesizer inferred latches to hold the output when conditions were not met.  

![printing_statistics](.Screenshots/ps_incomp_if.jpg)

- Here the stats perfectly shows the `mux` beccomes ` D-Latch` as we expected.
- So improper coding style or inconsistent code leads to `inferred latches`.

---


![graphical view](.Screenshots/synth_incomp_if.jpg)

---

## 2. 2nd Example (incomp_if_2.v)


### Code Analysis

- The Verilog source code clearly shows missing else conditions.  

![Verilog code (incomp_if_2.v)](.Screenshots/code_incomp_if2.jpg)

---

### RTL Simulation

- We first ran an RTL simulation to observe the output behavior of the incomplete if statements.  

![ RTL simulation result 2](.Screenshots/rtl_incomp_if2.jpg)

- Here also the else condition is missing
- inorder to work the above logic mentioned in the code, the `enable condition` of th3 `latch` will be `~(i0 + ~(i2))`.
- This will leads to working of above logic , else the output y will latch into previous value.

---

### Synthesis printing statistics and Graphical View 

- After synthesis, we observed that the synthesizer inferred latches to hold the output when conditions were not met.  

![printing_statistics](.Screenshots/ps_incomp_if2.jpg)

- YEs, the printed stats also proved the prsence of latch.

                                
![graphical view](.Screenshots/synth_incomp_if2.jpg)
---


## Observations
- Incomplete if statements result in **latch inference**.  
- Simulation may still run correctly, but synthesis introduces additional hardware to hold values.  
- To avoid this, always write **complete if-else statements**.  

---
