# 2. Labs on GLS & Synthesis-Simulation Mismatch

In this subdivision, we performed **hands-on labs** to understand how GLS helps detect synthesis-simulation mismatches. We used the following files:

- `ternary_operator_mux.v`  
- `bad_mux.v`  
- `good_mux.v`  

---

## 1. Lab Procedure

1. **Simulate the RTL**  
   - First, we simulated `ternary_operator_mux.v` at the RTL level.  
   - Verified its logical correctness before synthesis.

2. **Synthesize the design**  
   - Generated the gate-level netlist for the design.  

3. **Gate-Level Simulation (GLS)**  
   
- To perform GLS, we need to invoke **iVerilog**:

```bash
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v <module_name_net.v> <testbench_name.v>
```

- Generate the simulation executable:

```bash
./a.out
```
- To see the waveform :

```bash
gtkwave < testbench_name.vcd >
```

---

## Analysis of ternary_operator_mux.v

**1. RTL Code Screenshot:**  

![RTL Code](.Screenshots/ternary_operator_mux_code.jpg)


**2. RTL Simulation Waveform:**

![RTL Simulation](.Screenshots/ternary_operator_mux_rtl.jpg)


**3. Synthesized printing statitics:**

![Synthesis Screenshot](.Screenshots/synthesis_ss.jpg)


**4. Graphical Representation:**

![Show Screenshot](.Screenshots/show.jpg)


- In `ternary_operator_mux.v` is the efficient way of coding 2*1 mux.
- The RTL simulation works well for the `ternary_operator_mux.v`

---

## Analysis of bad_mux.v


**1. RTL Code Screenshot:**  

![RTL Code](.Screenshots/bad_mux_code.jpg)


**2. RTL Simulation Waveform:**

![RTL Simulation](.Screenshots/bad_mux_rtl.jpg)


**3. Synthesized printing statitics:**

![Synthesis Screenshot](.Screenshots/synthesis_ss2.jpg)


**4. Graphical Representation:**

![Show Screenshot](.Screenshots/show2.jpg)


- In `bad_mux.v` is the bad way of coding , because it only active to the sensitivity list sel, eventhough the input i0 & i1 varies.
- so the characteristics of mux is not followed here.
- so it leads to the synthesis - simulation mismatch.

---


## Observations

- GLS uses the gate-level netlist as the Design Under Test (DUT).
- Any mismatches between RTL simulation and gate-level behavior can be observed here.
- This lab demonstrated why GLS is essential before moving to layout: small RTL issues can appear as major functional errors at the gate level.