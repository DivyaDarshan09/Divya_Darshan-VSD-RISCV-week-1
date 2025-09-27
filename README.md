# Week 1 - RISC-V SoC Tapeout Journey (Divya Darshan)
---

[![Repo Size](https://img.shields.io/github/repo-size/DivyaDarshan09/Divya_Darshan-VSD-RISCV-week-1)](https://github.com/DivyaDarshan09/Divya_Darshan-VSD-RISCV-week-1)
[![Owner](https://img.shields.io/badge/Owner-DivyaDarshan09-blue)](https://github.com/DivyaDarshan09)

This repository documents the work done in Week 1 of my 20-week RISC-V SoC Tapeout project powered by VLSI System Design (VSD) and IIT Gandhinagar.

---

##  Table of Contents

- [Week 1 - RISC-V SoC Tapeout Journey (Divya Darshan)](#week-1---risc-v-soc-tapeout-journey-divya-darshan)
- [Repository Structure](#repository-structure)
  - [Day-1](#day-1)
    - [1-Introduction-to-iVerilog](Day-1/1-Introduction-to-iVerilog/Readme.md)
    - [2-Labs-using-iVerilog-GTKwave](Day-1/2-Labs-using-iVerilog-GTKwave/Readme.md)
    - [3-Introduction-to-Yosys-Logic-Synthesis](Day-1/3-Introduction-to-Yosys-Logic-Synthesis/Readme.md)
    - [4-Labs-using-Yosys-Sky130-PDK](Day-1/4-Labs-using-Yosys-Sky130-PDK/Readme.md)
  - [Day-2](#day-2)
    - [1-Introduction-to-Timing-Libs](Day-2/1-Introduction-to-Timing-Libs/Readme.md)
    - [2-Hierarchical-vs-Flat-Synthesis](Day-2/2-Hierarchical-vs-Flat-Synthesis/Readme.md)
    - [3-Various-Flop-Coding-Styles-and-Optimizations](Day-2/3-Various-Flop-Coding-Styles-and-Optimizations/Readme.md)
  - [Day-3](#day-3)
    - [Intro_to_Optimization](Day-3/Intro_to_Optimization/Readme.md)
    - [Combinational_Logic_Optimization](Day-3/Combinational_Logic_Optimization/Readme.md)
    - [Sequential_Logic_Optimization](Day-3/Sequential_Logic_Optimization/Readme.md)
    - [Sequential_Optimization_for_Unused_Outputs](Day-3/Sequential_Optimization_for_Unused_Outputs/Readme.md)
  - [Day-4](#day-4)
    - [GLS & Synthesis–Simulation Mismatch + Blocking/Non-Blocking Mismatch](Day-4/GLS%20&%20Synthesis%E2%80%93Simulation%20Mismatch%20+%20Blocking/Non-Blocking%20Mismatch/Readme.md)
    - [Labs on GLS & Synthesis–Simulation Mismatch](Day-4/Labs%20on%20GLS%20&%20Synthesis%E2%80%93Simulation%20Mismatch/Readme.md)
    - [Labs on Synthesis–Simulation Mismatch for Blocking Statements](Day-4/Labs%20on%20Synthesis%E2%80%93Simulation%20Mismatch%20for%20Blocking%20Statements/Readme.md)
  - [Day-5](#day-5)
    - [If-Case_Constructs](Day-5/If-Case_Constructs/Readme.md)
    - [Incomplete_If-Case](Day-5/Incomplete_If-Case/Readme.md)
    - [Incomplete_Overlapping_Case](Day-5/Incomplete_Overlapping_Case/Readme.md)
    - [For-Loop_Generate](Day-5/For-Loop_Generate/Readme.md)
    - [Labs_For-Loop_Generate](Day-5/Labs_For-Loop_Generate/Readme.md)
- [Week 1 Topics Covered](#Week -1 Topics Covered)
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

## Week -1 Topics Covered

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

--

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