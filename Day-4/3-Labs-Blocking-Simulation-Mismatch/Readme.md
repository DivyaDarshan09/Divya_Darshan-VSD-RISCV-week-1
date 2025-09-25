# 3. Labs on Synthesis-Simulation Mismatch for Blocking Statements

In this final subdivision of Day 4, we explored **synthesis-simulation mismatches caused by blocking assignments**.  

We used the Verilog module:

- `blocking_caveat.v` – a combinational logic circuit combining **AND** and **OR** gates.

---

## 1. Lab Procedure

1. **RTL Simulation**  
   - Simulated `blocking_kv8.v` at the RTL level.  
   - Verified logical behavior of the combinational circuit.  
   - Observed the waveform and identified how **blocking assignments** affect signal updates.  

2. **Synthesis & GLS Simulation**  
   - Synthesized the design to generate the **gate-level netlist**.  
   - Ran **GLS** to simulate the synthesized netlist.  
   - Compared GLS waveform with RTL simulation to identify mismatches.  

---

## 2. Observations

- In RTL simulation:  
  - Some signals depended on **older values** of other variables due to blocking assignments (`=`).  
  - This behavior sometimes **mimics flip-flops**, even in combinational logic.  

- In GLS simulation:  
  - The synthesized design performed correctly according to hardware logic.  
  - A clear **synthesis-simulation mismatch** was observed between RTL and GLS waveforms.  

- **Lesson:**  
  - Blocking assignments in combinational logic can introduce **unexpected sequential behavior** in RTL simulation.  
  - GLS is necessary to confirm the **actual hardware functionality**.  

---

## 3. Screenshots

**1. Verilog Code Screenshot:**  

![Blocking caveat Code](.Screenshots/blocking_caveat_code.jpg)

**2. RTL Simulation Waveform:** 

![RTL Waveform](.Screenshots/blocking_caveat_rtl.jpg)


**3. Synthesized Printed Statistics:**  

![Synthesized Details](.Screenshots/synth_bc.jpg)

**4. Graphical representation:**  

![Graphical Rep of blocking_caveat_module Details](.Screenshots/show.jpg)

**5. GLS Simulation Waveform:**  

![GLS Waveform](.Screenshots/blocking_caveat_gls.jpg)

  - In this waveform, the output `d` follows the combinational logic of the design where as when compared to RTL simulation, the output `d` holds the value of previous x value which acted as a flop.
  - Hence it shows `Synthesis-Simulation Mismatch`. 

---

