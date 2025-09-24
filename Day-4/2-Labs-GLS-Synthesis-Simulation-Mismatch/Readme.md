# Subdivision 2: Labs on GLS & Synthesis-Simulation Mismatch

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
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v < module_name.v > < testbench_name.v >
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

### Screenshots – Ternary Operator MUX Simulation

**1. RTL Simulation Waveform:**

![RTL Simulation](.Screenshots/ternary_operator_mux_rtl.png)

**2. GLS Simulation Waveform:**  

![GLS Simulation](.Screenshots/ternary_operator_mux_gls.png)


**3. RTL Code Screenshot:**  

![RTL Code](.Screenshots/ternary_operator_mux_code.png)


---


## Observations

- GLS uses the gate-level netlist as the Design Under Test (DUT).
- Any mismatches between RTL simulation and gate-level behavior can be observed here.
- This lab demonstrated why GLS is essential before moving to layout: small RTL issues can appear as major functional errors at the gate level.