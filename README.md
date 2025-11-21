# 32-bit Ripple Carry Adder (Verilog HDL)

This project implements a 32-bit Ripple Carry Adder (RCA) using Verilog HDL.  
It includes design, simulation, testbench verification, and FPGA synthesis analysis.

---

## 1. Introduction

A Ripple Carry Adder adds two binary numbers using a chain of 1-bit full adders.  
Each stage waits for the carry from the previous stage, producing the characteristic "ripple" delay.

This project covers:
- Verilog-based RCA design  
- Simulation and waveform verification  
- RTL and technology schematic generation  
- FPGA resource utilization analysis

---

## 2. Design Methodology

### Ripple Carry Adder Overview
- The 32-bit RCA is constructed from **32 full-adder modules**.  
- Each full adder takes inputs (A, B, Cin) and produces (Sum, Cout).  
- Carry propagates from the least significant bit (LSB) to the most significant bit (MSB).

### Architecture

FA0 -> FA1 -> FA2 -> ... -> FA31


- FA0 receives external carry-in (Cin = 0)  
- FA31 produces the final carry-out (Cout)

---

## 3. Testbench and Simulation

### Testbench Features
- Applies multiple test vectors  
- Validates sum and carry-out  
- Checks ripple delay behavior  
- Ensures correct functioning across all 32 stages  

### Results
- Sum bits stabilize only after the carry finishes propagating through all stages  
- Cout matches expected values  
- The ripple effect is clearly observed in the waveform

---

## 4. Synthesis (Quartus)

### RTL Schematic
- Shows all 32 full adders connected sequentially  
- Visual representation of carry chain and sum lines  

### Technology Schematic
- Maps logic to FPGA LUTs and combinational elements  
- Illustrates internal gate-level implementation  

---

## 5. Device Utilization (FPGA)

Resource usage summary:
- **Combinational ALUTs:** 63  
- **I/O Pins:** 97  
- **Total Fan-out:** 375  
- **Flip-flops:** None (purely combinational circuit)

---

## 6. Conclusion

The 32-bit Ripple Carry Adder was successfully designed and simulated.  
Waveforms confirmed correct functionality, and synthesis reports showed efficient resource usage.

This project demonstrates understanding of:
- Verilog structural modeling  
- Carry propagation logic  
- Combinational circuit design  
- FPGA RTL and technology mapping  

---

## Project Files

📂 32bit-ripple-carry-adder
 ├── Verilog CODE
 ├── Testbench
 ├── 32_Bit-Ripple_Carry_Adder.docx
 └── README.md
