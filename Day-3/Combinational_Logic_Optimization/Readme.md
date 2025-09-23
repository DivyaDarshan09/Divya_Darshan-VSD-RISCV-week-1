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

  ![Verilog Screenshot](.screenshots/OPT-check_verilog.png) 


- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.screenshots/OPT-check_synth.png) 


- **Screenshot: Graphical Representation**

  ![Graphical Representation](.screenshots/OPT-check_graph.png)  


---

##  OPT-check2.v (OR Gate)

- **Screenshot: Verilog (OPT-check2.v)**  

  ![Verilog Screenshot](.screenshots/OPT-check2_verilog.png)  


- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.screenshots/OPT-check2_synth.png) 


- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.screenshots/OPT-check2_graph.png)  



---

## OPT-check3.v (3-input AND Gate)

- **Screenshot: Verilog (OPT-check3.v)**  

  ![Verilog Screenshot](.screenshots/OPT-check3_verilog.png)  


- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.screenshots/OPT-check3_synth.png)  


- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.screenshots/OPT-check3_graph.png)  

---

##  Lab Experiments

###  Lab 1 – OPT-check4.v

- Experimenting with combinational block.  
- Applied **constant propagation + synthesis**.  
- Observed how redundant logic gets reduced to a minimal form.  

- **Screenshot: Verilog (OPT-check4.v)**

  ![Verilog Screenshot](.screenshots/OPT-check4_verilog.png) 


- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.screenshots/OPT-check4_synth.png)  


- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.screenshots/OPT-check4_graph.png)  

---

###  Lab 2 – multiple_module_OPT.v

- Contains **multiple modules** that interact.  
- Applied **opt_clean -purge** before ABC mapping.  
- Each module was optimized independently.  

- **Screenshot: Verilog (multiple_module_OPT.v)**  

  ![Verilog Screenshot](.screenshots/multiple_module_verilog.png)  


- **Screenshot: Synthesis Log**  

  ![Synthesis Log](.screenshots/multiple_module_synth.png)


- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.screenshots/multiple_module_graph.png)  

---

## Key Learning

- Combinational optimization is achieved using constant propagation.
- `opt_clean -purge` is mandatory before `abc -liberty` command for proper optimization.
- Complex-looking Verilog simplifies into basic logic gates after optimization.
- Multiple modules can be optimized separately, reducing redundancy.

---