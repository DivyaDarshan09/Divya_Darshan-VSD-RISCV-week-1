# Week 1 - RISC-V SoC Tapeout Journey (Divya Darshan)
---

[![Repo Size](https://img.shields.io/github/repo-size/DivyaDarshan09/Divya_Darshan-VSD-RISCV-week-1)](https://github.com/DivyaDarshan09/Divya_Darshan-VSD-RISCV-week-1)
[![Owner](https://img.shields.io/badge/Owner-DivyaDarshan09-red)](https://github.com/DivyaDarshan09)

This repository documents the work done in Week 1 of my 20-week RISC-V SoC Tapeout project powered by VLSI System Design (VSD) and IIT Gandhinagar.

---

##  Table of Contents

- [Week 1 - RISC-V SoC Tapeout Journey (Divya Darshan)](#week-1---risc-v-soc-tapeout-journey-divya-darshan)
- [Repository Structure](#repository-structure)
  - [Day-1](#day-1)
  - [Day-2](#day-2)
  - [Day-3](#day-3)
  - [Day-4](#day-4)
  - [Day-5](#day-5)
- [Week 1 Topics Covered](#week-1-topics-covered)
- [Tools Used](#tools-used)
- [What I Learned](#what-i-learned)
- [Next Steps](#next-steps)
- [Author](#author)
- [Credits & Acknowledgments](#credits--acknowledgments)


---

##  Repository Structure

```tree 
Day-1/
├── 1-Introduction-to-iVerilog/
│   └── Readme.md
│
├── 2-Labs-using-iVerilog-GTKwave/
│   └── Readme.md
│
├── 3-Introduction-to-Yosys-Logic-Synthesis/
│   └── Readme.md
│
└── 4-Labs-using-Yosys-Sky130-PDK/
    └── Readme.md

Day-2/
├── 1-Introduction-to-Timing-Libs/
│   └── Readme.md
├── 2-Hierarchical-vs-Flat-Synthesis/
│   └── Readme.md
└── 3-Various-Flop-Coding-Styles-and-Optimizations/
    └── Readme.md

Day-3/
│── README.md         
│
├── Intro_to_Optimization/
│   └── README.md
│
├── Combinational_Logic_Optimization/
│   └── README.md
│
├── Sequential_Logic_Optimization/
│   └── README.md
│
└── Sequential_Optimization_for_Unused_Outputs/
    └── README.md

Day4/
│── README.md 
│
├── GLS & Synthesis–Simulation Mismatch + Blocking/Non-Blocking Mismatch/
│ └── README.md 
│
├── Labs on GLS & Synthesis–Simulation Mismatch/
│ └── README.md 
│
└── Labs on Synthesis–Simulation Mismatch for Blocking Statements/
  └── README.md 

Day-5/
│── README.md 
│
├── If-Case_Constructs/
│ └── README.md
│
├── Incomplete_If-Case/
│ └── README.md
│
├── Incomplete_Overlapping_Case/
│ └── README.md
│
├── For-Loop_Generate/
│ └── README.md
│
└── Labs_For-Loop_Generate/
  └── README.md
```
---

## Week 1 Topics Covered

- **Day-1**: Introduction to Verilog RTL Design and Synthesis.  
- **Day-2**: Timing Libs, Hierarchical vs Flat Synthesis & Efficient Loop Coding Styles.
- **Day-3**: Combinational and Sequential Optimization.  
- **Day-4**: GLS, Blocking vs Non-Blocking & Synthesis-Simulation Mismatch.  
- **Day-5**: Optimization in Synthesis.

### Each day folder contains:
- Basic definition
- Verilog code files
- Simulation files and screenshots
- Synthesized printing stats and graphical representation of the design
- README describing tasks and observations

---
## Tools Used 

| Tool                     | Purpose / Use Case                                      |
|--------------------------|--------------------------------------------------------|
| Icarus Verilog (iverilog)| Compiling and simulating Verilog/SystemVerilog code    |
| GTKWave                  | Viewing and analyzing waveform outputs                |
| Yosys                    | Synthesizing Verilog designs to gate-level netlists   |

---

##  What I learned
- Understood the need of simulator and synthesizer.
- Got hands on with digital designs using the tools.
- Understood the importance of library files (.lib) and the cells present in it
- Understood the flow of synthesis and types of synthesis using the synthesizer `yosys`
- Understood the combinational and sequential design optimization in rtl
- Understood the concept and need of Gate level Simulation, blocking & non-blocking contructs and synthesis-simulation mismatch.
- Understood how optimization makes the design simple and reduce the area and power of a chip.
- Finally realized efficient coding styles for flops, looping constructs, combinational and sequential logic.

---

## Next Steps
- Continue documenting tasks for upcoming weeks.
- Maintain consistency in structure for all weeks.

---

##  Author
- **Divya Darshan VR** – [GitHub](https://github.com/DivyaDarshan09)
- 👉 [Read Authorship Declaration](AUTHORS.md)

---

## Credits & Acknowledgments
I would like to express my gratitude to:

- **Kunal Ghosh**, Founder of **VLSI System Design (VSD)** and his team, for providing this wonderful opportunity and platform.
- **IIT Gandhinagar** for collaborating and supporting the RISC-V SoC Tapeout program.
- The VSD community, which is actively contributing to building India's semiconductor ecosystem and leading towards self-reliance in chip design and innovation.
- This initiative will truly accelerate India's growth in semiconductors, empower students and professionals, and inspire future VLSI engineers.

---
