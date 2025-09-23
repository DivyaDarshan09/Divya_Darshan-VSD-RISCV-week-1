# 2. Combinational Logic Optimization

In this subdivision, we focused on **combinational logic optimization**.  
We mainly worked with the **OPT files** (`OPT-check.v`, `OPT-check2.v`, `OPT-check3.v`, `OPT-check4.v`, etc.), along with their corresponding **relog files**.  

The main idea was to perform **constant propagation** and simplify the designs into basic logic gates.  

---

## Files Overview

- **OPT-check.v** → Simplifies into an **AND gate**  
- **OPT-check2.v** → Simplifies into an **OR gate**  
- **OPT-check3.v** → Simplifies into a **3-input AND gate**  
- **OPT-check4.v** → Used for **Lab Experiment 1**  
- **multiple_module_OPT.v** → Used for **Lab Experiment 2**

We also learned about **multiple modules** in `multiple_module_OPT.v` where different blocks are optimized individually.

---

## Command for Constant Propagation

Before running synthesis and ABC mapping, we must perform constant propagation with:

```bash
opt_clean -purge
```
- This ensures redundant constants are removed and optimization happens properly.

---

## OPT-check.v (AND Gate)

- **Screenshot: Verilog (OPT-check.v)**  

  ![Verilog Screenshot](.Screenshots/OPT-check_verilog.jpg) 

---

- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.Screenshots/OPT-check_synth.jpg) 

  - as the verilog code shows its a multiplexer the synthesizer optimized it into an AND gate.

---

- **Screenshot: Graphical Representation**

  ![Graphical Representation](.Screenshots/OPT-check_graph.jpg)  

---

##  OPT-check2.v (OR Gate)

- **Screenshot: Verilog (OPT-check2.v)**  

  ![Verilog Screenshot](.Screenshots/OPT-check2_verilog.jpg)  

---

- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.Screenshots/OPT-check2_synth.jpg) 

- Here the design is simplified into an OR gate
---

- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.Screenshots/OPT-check2_graph.jpg)  

---

## OPT-check3.v (3-input AND Gate)

- **Screenshot: Verilog (OPT-check3.v)**  

  ![Verilog Screenshot](.Screenshots/OPT-check3_verilog.jpg)  

---

- **Screenshot: Synthesis Log**  

  ![Synthesis Log](Sscreenshots/OPT-check3_synth.jpg)  

  - Here the design is simplified into an 3 input AND gate.

---

- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.Screenshots/OPT-check3_graph.jpg)  

---

##  Lab Experiments

###  Lab 1 – OPT-check4.v

- Experimenting with combinational block.  
- Applied **constant propagation + synthesis**.  
- Observed how redundant logic gets reduced to a minimal form.  

- **Screenshot: Verilog (OPT-check4.v)**

  ![Verilog Screenshot](.Screenshots/OPT-check4_verilog.jpg) 

---

- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.Screenshots/OPT-check4_synth.jpg)

  - The design is simplified into an XNOR gate.  

---

- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.Screenshots/OPT-check4_graph.jpg)  

---

###  Lab 2 – multiple_module_OPT.v

- Contains **multiple modules** that interact.  
- Applied **opt_clean -purge** before ABC mapping.  
- Each module was optimized independently.  

- **Screenshot: Verilog (multiple_module_OPT.v)**  

  ![Verilog Screenshot](.Screenshots/multiple_module_verilog.jpg)  

---

- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.Screenshots/multiple_module_synth.jpg)

---

- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.Screenshots/multiple_module_graph.jpg)  

---

## Key Learning

- Combinational optimization is achieved using constant propagation.
- `opt_clean -purge` is mandatory before `abc -liberty` command for proper optimization.
- Complex-looking Verilog simplifies into basic logic gates after optimization.
- Multiple modules can be optimized separately, reducing redundancy.

---