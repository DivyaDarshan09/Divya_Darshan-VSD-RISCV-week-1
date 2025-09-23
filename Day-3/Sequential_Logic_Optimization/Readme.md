# 3. Sequential Logic Optimization

In this subdivision, I focused on **sequential logic optimization**.  
I analyzed and synthesized several **D flip-flop (dff)** based modules with constant inputs, observing how the synthesis tool optimizes redundant logic.

---

##  What I Learned

- Sequential constant propagation is very effective in removing redundant flip-flops when outputs are constant.  
- Synthesis tools can optimize DFF-based modules into simpler logic (like wires) if possible, saving area.  
- Observing synthesis statistics and graphical representation helps me understand how the tool interprets my RTL.  
- Understanding sequential optimization helps me write **more efficient RTL** for state machines and memory elements.  

---

##  Files Analyzed
 
1. **dff_const1**  
2. **dff_const2**  
3. **dff_const3**  

I performed **Verilog code analysis**, **synthesis**, and studied the **graphical representation** of each design.  

---

##  dff_const1

- **Observation:** Standard DFF; output depends on input.  
- Synthesizer prints DFFs correctly.  

- **Key Learnings:**  
  - Confirms correct mapping of flip-flops.  
  - Useful for sequential logic verification.  

- **Screenshot: Verilog Module**  

  ![Verilog Screenshot](.screenshots/dff_const1_verilog.jpg)  

---

- **Screenshot: Synthesis Statistics**  

  ![Synthesis Stats](.screenshots/dff_const1_synth.jpg)  

  - Here there is no possiblity of optimizing the design hence 1 DFF is used.

  ---

- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.screenshots/dff_const1_graph.jpg)  

---

##  dff_const2

- **Observation:** Output is **always 1** regardless of inputs or reset.  
- Synthesizer optimized logic into a **wire**, no DFFs printed.  

- **Key Learnings:**  
  - Sequential constant propagation removes redundant flip-flops.  
  - Recognizing constant outputs helps simplify the design.  

- **Screenshot: Verilog Module**  

  ![Verilog Screenshot](.screenshots/dff_const2_verilog.jpg)  

  ---

- **Screenshot: Synthesis Statistics**  

  ![Synthesis Stats](.screenshots/dff_const2_synth.jpg) 

  - Here the DFF is always logic 1 **independent of input and reset** . Hence DFF is optimized into a logic 1 wire.

  --- 

- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.screenshots/dff_const2_graph.jpg)  

---

##  dff_const3

- **Observation:** Similar to const2; constant output optimized.  
- Synthesizer reduces redundant flip-flops.  

- **Key Learnings:**  
  - Constant outputs in sequential circuits can be optimized to **wires**.  
  - Helps save area and reduce unnecessary hardware.  

- **Screenshot: Verilog Module**  

  ![Verilog Screenshot](.screenshots/dff_const3_verilog.jpg)  

  ---

- **Screenshot: Synthesis Statistics**  

  ![Synthesis Stats](.screenshots/dff_const3_synth.jpg)  

  ---

- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.screenshots/dff_const3_graph.jpg) 


---

##  Lab Experiments

###  Lab 1 – dff_const4

- Performed analysis and synthesis for sequential optimization.  
- Redundant flip-flops removed wherever possible.  

- **Screenshot: Verilog Module**  

  ![Verilog Screenshot](.screenshots/dff_const4_verilog.jpg)  

---

- **Screenshot: Synthesis Statistics**  

  ![Synthesis Stats](.screenshots/dff_const4_synth.jpg)  

---

- **Screenshot: Graphical Representation**  

  ![Graphical Representation](.screenshots/dff_const4_graph.jpg)  

---

###  Lab 2 – dff_const5

- Similar analysis and optimization as const4.  
- Synthesizer removes unnecessary flip-flops and simplifies logic.  

- **Screenshot: Verilog Module**  

  ![Verilog Screenshot](.screenshots/dff_const5_verilog.jpg)  

  ---

- **Screenshot: Synthesis Statistics**  

  ![Synthesis Stats](.screenshots/dff_const5_synth.jpg)  

  ---

- **Screenshot: Graphical Representation**  
  ![Graphical Representation](.screenshots/dff_const5_graph.jpg)  


---