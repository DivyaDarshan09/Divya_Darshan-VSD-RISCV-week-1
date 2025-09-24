# 1. GLS, Synthesis-Simulation Mismatch & Blocking/Non-Blocking Mismatches

This subdivision covers **Gate-Level Simulation (GLS)**, why it is needed, and how **synthesis-simulation mismatches** occur due to coding practices, especially **blocking vs non-blocking assignments**.

---

## 1. Gate-Level Simulation (GLS)

**Definition:**  
GLS is the process of running a testbench using the **netlist** as the Design Under Test (DUT). The netlist is logically equivalent to the RTL in terms of ports.

**DUT (Design Under Test):**  
The DUT is the component or design being tested in the simulation. In GLS, the DUT is the **synthesized netlist**.

**Why GLS is needed:**  
- To verify the **logical correctness** of the design after synthesis.  
- To ensure the **timing of the design** is met.  

**Delay Annotation:**  
GLS often requires **delay annotation**, which adds timing information from the synthesis tool to the gate-level netlist. This allows the simulation to reflect real timing delays in the hardware.  

**High-Level Block Diagram:**  

![GLS Block Diagram](./.screenshots/gls_block_diagram.png) 

*Note:* If gate-level Verilog models are **delay-annotated**, GLS can be used for **timing validation**.

---

## 2. Gate-Level Verilog Model

- A gate-level Verilog model represents the synthesized cells of a design.  
- Example: An AND gate in the design might be mapped to a synthesized cell named `ANDX1` with corresponding input/output ports.  
- The model defines **functionality** of the synthesized cell, though the actual cell name may not directly reflect the logic function.  

**Types of Gate-Level Models:**  
1. **Timing-Aware:** Includes both functionality and timing (out of scope for now).  
2. **Functionality Only:** Focuses only on logical behavior. This is what we use for verification in this course.  

---

## 3. Synthesis-Simulation Mismatch

**Definition:**  
A mismatch occurs when the **RTL simulation** behavior does not match the **post-synthesis GLS** behavior.

**Common Causes:**  
1. Missing or incomplete sensitivity lists  
2. Incorrect use of blocking (`=`) vs non-blocking (`<=`) assignments  
3. Non-standard Verilog coding styles  

---

### 3.1 Missing Sensitivity List

- Example: 2-to-1 MUX  
- In a simulator, outputs change **only when the inputs change**.  
- If the sensitivity list is incomplete, some input changes will **not trigger** the always block, leading to incorrect behavior.  
- Fix: Use `@(*)` event-driven sensitivity list to include all relevant inputs.  

---

### 3.2 Blocking vs Non-Blocking Assignments

**Blocking (`=`):**  
- Executes statements **in order**, one after the other.  
- Can cause simulation-only behavior that does not match synthesized hardware.

**Non-Blocking (`<=`):**  
- RHS expressions are evaluated **in parallel** and assigned to LHS at the end of the time step.  
- Matches hardware behavior more accurately.  

**Example 1 – Shift Register (Sequential Logic):**  
```verilog
always @(posedge clk) begin
    q0 = d;
    q1 = q0;
end

```
---

### Example – Sequential Logic (Shift Register)

### Shift Register Example – Blocking Assignments

- shift reg logic 
```verilog
always @(posedge clk or posedge rst) begin
        if (rst) begin
            q0 = 0;
            q = 0;
        end else begin
            q0 = d;
            q = q0; 
        end
    end
endmodule

```
- Here the design needs 2 flops. 
- Lets see if we changed the order of execution.

```verilog
    always @(posedge clk or posedge rst) begin
        if (rst) begin
            q0 = 0;
            q = 0;
        end else begin
            q0 = d;
            q = q0; 
        end
    end
endmodule

``` 
- Using blocking assignments here produces only **one flip-flop effect** instead of two, because `q1` depends on the updated `q0`.

**Lesson:** Always use **non-blocking assignments (`<=`)** when designing sequential circuits.

---

### Example – Combinational Logic

```verilog
always @(*) begin
    y = q0 & c;
    q0 = a | b;
end

```
- y depends on the old value of q0 because of blocking order.
- This may inadvertently turn combinational logic into a sequential-like behavior (introduces flops).
- Fix: Reorder statements or use non-blocking assignments where appropriate.

---

## Key Takeaways

- GLS is essential for post-synthesis verification.
- Missing sensitivity lists can cause simulation-only behavior.
- Blocking vs non-blocking assignments are critical for matching RTL to hardware.
- Always run GLS to detect potential synthesis-simulation mismatches.

---