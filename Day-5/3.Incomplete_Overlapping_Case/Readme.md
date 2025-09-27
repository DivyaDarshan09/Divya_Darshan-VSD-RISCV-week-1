# Labs on Incomplete Overlapping Case

This document explains the third subdivision of **Day 5 - Optimization in Synthesis**.  
In this section, we studied how **incomplete case statements and overlapping case statements** affect simulation and synthesis.

---

## Files Used
1. `incomp_case.v` – Incomplete case example  
2. `comp_case.v` – Complete case example  
3. `partial_case.v` – Partial assignment in case  
4. `bad_case.v` – Overlapping case example  

---

## Concept: Incomplete and Overlapping Case
- **Incomplete Case**: If not all possibilities are covered and no `default` is present → synthesizer infers latches.  
- **Partial Case**: If all branches don’t assign all outputs → latches may be inferred.  
- **Overlapping Case**: If more than one case condition is true, multiple branches can execute → synthesis results may differ from simulation.  
- **Complete Case**: All conditions are covered or a `default` is provided → no latch inference.  

---

## Analysis of Files

### 1. Incomplete Case (`incomp_case.v`)
- Code contained missing conditions without a default branch.  
- Simulation executed but synthesis inferred latches.  

![Code Screenshot](.Screenshots/code_incomp_case.jpg)  

![RTL Simulation](.Screenshots/rtl_incomp_case.jpg)  

![Synthesis Graph](.Screenshots/synth_incomp_case.jpg)  

---

### 2. Complete Case (`comp_case.v`)
- All conditions covered, or a default branch was used.  
- No latch inference during synthesis.  

![Code Screenshot](.Screenshots/code_comp_case.jpg)  

![RTL Simulation](.Screenshots/rtl_comp_case.jpg)  

![Synthesis Graph](.Screenshots/synth_comp_case.jpg)  

---

### 3. Partial Assignment Case (`partial_case.v`)
- Outputs were not fully assigned in all branches.  
- Resulted in latch inference.  
- Best practice is to assign **all outputs in all case branches**.  

![Code Screenshot](.Screenshots/code_partial_case.jpg) 

![RTL Simulation](.Screenshots/rtl_partial_case.jpg) 

![Synthesis Graph](.Screenshots/synth_partial_case.jpg)  

---

### 4. Bad Case (Overlapping) (`bad_case.v`)
- Multiple case branches overlapped (more than one condition could be true).  
- RTL simulation produced outputs, but synthesis showed mismatches due to ambiguity.  
- Overlapping cases are **unpredictable** and must be avoided.  

![Code Screenshot](.Screenshots/code_bad_case.jpg)

![RTL Simulation](.Screenshots/rtl_bad_case.jpg) 

![Synthesis Graph](.Screenshots/synth_bad_case.jpg)  

---

## Observations
- Incomplete case statements lead to latch inference.  
- Partial assignment in case statements also causes latch inference.  
- Overlapping cases result in **unpredictable outputs** and mismatches between simulation and synthesis.  
- Complete cases with a `default` branch are the correct coding style.  

---

## What I Learned
- Always use a **default branch** in case statements to avoid latches.  
- Assign **all outputs in every case branch** to ensure consistent synthesis results.  
- Avoid overlapping conditions in case statements, as they may cause hardware mismatches.  
- Good coding practice in case statements leads to **predictable and optimized hardware**.  

---

## Summary Comparison Table

| Case Type              | Behavior in Simulation                 | Behavior in Synthesis                | Risk / Issue                  | Best Practice                          |
|-------------------------|----------------------------------------|--------------------------------------|--------------------------------|----------------------------------------|
| **Incomplete Case**    | Produces output for given cases only   | Infers latches for missing cases     | Latch inference                | Always include `default` branch        |
| **Complete Case**      | Works for all inputs                   | Synthesizes cleanly, no latches      | No major issues                | Cover all cases or add `default`       |
| **Partial Assignment** | Produces outputs for some signals only | Latch inference for unassigned ones  | Incomplete hardware assignment | Assign **all outputs** in all branches |
| **Overlapping Case**   | Multiple matches may be executed       | Unpredictable hardware behavior      | Simulation vs synthesis mismatch | Ensure **no overlapping conditions**   |

---