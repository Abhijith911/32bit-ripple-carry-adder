# 🔢 32-bit Ripple Carry Adder in Verilog HDL

<p align="center">
  <img src="https://img.shields.io/badge/Language-Verilog%20HDL-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Tool-Intel%20Quartus%20Prime-lightblue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Simulation-ModelSim-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Design-RTL%20%2F%20FPGA-orange?style=for-the-badge"/>
</p>

<p align="center">
  A 32-bit Ripple Carry Adder designed in <strong>Verilog HDL</strong>, synthesized in <strong>Intel Quartus Prime</strong>,<br/>
  and verified with <strong>ModelSim</strong> waveform simulation — following the same RTL workflow used in professional ASIC and FPGA development.
</p>

---

## 🎯 Overview

A Ripple Carry Adder adds two binary numbers using a chain of 1-bit full adders. Each stage waits for the carry output from the previous stage, producing the characteristic "ripple" delay from LSB to MSB.

| Property | Details |
|---|---|
| Design | 32-bit Ripple Carry Adder |
| Language | Verilog HDL |
| Synthesis Tool | Intel Quartus Prime |
| Simulation | ModelSim |
| Circuit Type | Purely combinational (no flip-flops) |

---

## 🏗️ Architecture

The 32-bit RCA is built from **32 cascaded full-adder modules**:

```
Cin → [FA0] → [FA1] → [FA2] → ... → [FA31] → Cout
        S0      S1      S2             S31
```

- Each full adder takes inputs **(A, B, Cin)** and produces **(Sum, Cout)**
- **FA0** receives the external carry-in (`Cin = 0`)
- **FA31** produces the final carry-out (`Cout`)
- Carry propagates sequentially from LSB → MSB

---

## 🧪 Testbench & Simulation

### Testbench Features
- Applies multiple test vectors across all 32 stages
- Validates sum bits and carry-out for each input combination
- Verifies correct ripple delay behavior
- Confirms functioning across edge cases (overflow, all-ones, etc.)

### Simulation Results
- Sum bits stabilize only after carry finishes propagating through all 32 stages
- `Cout` matches expected values for all test vectors
- The ripple carry effect is clearly visible in ModelSim waveforms

---

## 📊 FPGA Synthesis Results (Quartus Prime)

### Device Utilization

| Resource | Usage |
|---|---|
| Combinational ALUTs | 63 |
| I/O Pins | 97 |
| Total Fan-out | 375 |
| Flip-flops | 0 (purely combinational) |

### Schematics Generated
- **RTL Schematic** — all 32 full adders connected sequentially, showing the carry chain and sum lines
- **Technology Schematic** — gate-level mapping to FPGA LUTs and combinational elements

---

## 📂 Project Structure

```
32bit-ripple-carry-adder/
├── ripple_carry_adder.v      # Top-level 32-bit RCA module
├── full_adder.v              # 1-bit full adder module
├── tb_ripple_carry_adder.v   # Testbench
├── 32_Bit-Ripple_Carry_Adder.docx  # Full project report
└── README.md
```

---

## 🚀 How to Simulate

### ModelSim
1. Open ModelSim and create a new project
2. Add `ripple_carry_adder.v`, `full_adder.v`, and `tb_ripple_carry_adder.v`
3. Compile all files
4. Run simulation on the testbench
5. Open waveform viewer to observe carry propagation

### Quartus Prime (Synthesis)
1. Create a new Quartus project
2. Add the Verilog source files
3. Set `ripple_carry_adder` as the top-level entity
4. Run **Analysis & Synthesis** to generate RTL and technology schematics
5. View resource utilization in the **Compilation Report**

---

## 🛠️ Tech Stack

| Category | Tool / Technology |
|---|---|
| HDL | Verilog |
| Synthesis | Intel Quartus Prime |
| Simulation | ModelSim |
| Design Type | RTL / Combinational Logic |
| Target | FPGA |

---
