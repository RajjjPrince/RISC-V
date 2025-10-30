# 🧠 RISC-V Processor Implementation  

A **Verilog-based RISC-V processor** design and simulation project using **Xilinx Vivado**.

---

## 🏷️ Badges

![Language](https://img.shields.io/badge/Language-Verilog-blue.svg)
![Tool](https://img.shields.io/badge/Tool-Xilinx%20Vivado-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

---

## 🖼️ Project Banner  



---

## 📘 Overview

This project implements a **32-bit RISC-V processor** based on the **RV32I** instruction-set architecture.  
It is designed, synthesized, and simulated in **Verilog HDL** using **Xilinx Vivado 2023.x**.

The design demonstrates a simple pipelined processor that executes arithmetic, logical, load/store, and branch instructions with proper control signal management.

---

## ⚙️ Key Features

- ✅ Implements **RV32I core instruction set**  
- ⚡ Supports arithmetic, logic, and branch operations  
- 🧩 Five pipeline stages — **Fetch | Decode | Execute | Memory | Writeback**  
- 💡 Modular Verilog HDL design  
- 🧪 Fully **testbench-verified**  
- 🔧 Synthesizable for **FPGA deployment**

---

## 🧩 Design Architecture

| Component | Description |
|------------|-------------|
| **Program Counter (PC)** | Maintains instruction sequencing |
| **Instruction Memory** | Stores 32-bit RISC-V machine code |
| **Register File** | 32 registers (x0–x31) for data storage |
| **ALU** | Performs arithmetic and logic operations |
| **Control Unit** | Generates control signals for data path modules |
| **Data Memory** | Used for load/store instructions |
| **Multiplexers** | Control data path flow |

---

---

## 🧪 Testbench & Simulation

The Verilog **testbench** validates the processor by:

- Initializing instruction memory with machine codes  
- Monitoring register & memory outputs  
- Checking correctness of executed instructions  

### 🧾 Example Test Program (Machine Code)

```verilog
mem[0] = 32'h00000013; // li x1, 0
mem[1] = 32'h00000113; // li x2, 0
mem[2] = 32'h002081b3; // add x3, x1, x2

## 📊 Block Diagram
![Block Diagram](./screenshots/Screenshot_2025-10-30_135937.png)


---

## 📷 Simulation Output

The **simulation results** demonstrate the correct functionality of the RISC-V processor.  
The waveform verifies signal transitions across each clock cycle, showing accurate instruction execution and data path activity.

### 🧩 Simulation Details

- Clock and reset signals initialized for synchronous operation  
- Register file values updated based on instruction sequence  
- ALU operations verified through waveform transitions  
- Data memory interactions (load/store) confirmed visually  
- Control signals (branch, memread, memwrite) validated for correctness  

### 🧮 Example Output Observations

| Signal | Description | Expected Behavior |
|---------|--------------|-------------------|
| **clk** | System clock | Toggles every cycle |
| **reset** | Processor reset | Initializes all registers and PC |
| **pc_out** | Program Counter output | Increments sequentially (or branches) |
| **alu_result** | Output of ALU | Matches operation result (e.g., add, sub, and) |
| **reg_write** | Register write enable | High when writing to register file |
| **mem_read/write** | Memory control | Active during load/store instructions |

---

### 🖼️ Add Your Simulation Waveform Here


> 📊 *The waveform above shows instruction execution flow and register/memory updates during behavioral simulation.*

---

### 🧮 Tools & Environment

| Tool | Version | Purpose |
|------|----------|----------|
| **Xilinx Vivado** | 2023.x or later | Design, synthesis, and simulation |
| **Verilog HDL** | IEEE-1364 | Processor design |
| **ModelSim / GTKWave** | Optional | Waveform visualization |
| **GitHub** | — | Version control & documentation |

---

---

## 🚀 How to Run

The project can be executed and simulated in **Xilinx Vivado** using the following steps:

### 🧰 Setup Instructions

1. **Clone the Repository**

   ```bash
   git clone https://github.com/<your-username>/riscv-processor.git
   cd riscv-processor



  2. Open the Project in Xilinx Vivado
    details:
      - Launch Vivado (version 2023.x or later)
      - Create a new RTL project
      - Add all Verilog source files from `src/` directory
      - Add the testbench file from `sim/` directory

  3. Run Behavioral Simulation
    details:
      - Set `tb_riscv.v` as the top-level simulation file
      - Run the simulation
      - Observe signal transitions and instruction execution in waveform viewer

   4. (Optional) Synthesize and Implement on FPGA
    details:
      - Target FPGA board (e.g., Xilinx Artix-7)
      - Run synthesis and implementation to validate real hardware performance
      - Use GTKWave or ModelSim for external waveform visualization

---

## 📂 Project Structure

repository: riscv-processor
description: Modular and scalable design for a 32-bit RISC-V processor project

structure:
  src/:
    - alu.v: Arithmetic Logic Unit
    - control_unit.v: Control signal generator
    - register_file.v: Register bank (x0–x31)
    - ...: Other modules (memory, PC, etc.)

  sim/:
    - tb_riscv.v: Testbench for processor verification

  screenshots/:
    - project_banner.png: Cover image or project logo
    - block_diagram.png: Processor architecture diagram
    - simulation_result.png: Simulation waveform output

  outputs/:
    - simulation.log: Log files from Vivado or ModelSim runs

  docs/:
    - README.md: Project documentation
    - riscv_project.yml: Project metadata/config file
    - LICENSE: License file (optional)

---

## 📈 Results

summary:
  - Implementation: "✅ Successfully implemented processor using Verilog HDL"
  - Verification: "🧠 Arithmetic, logic, and branch instructions verified via testbench"
  - Timing: "⚙️ Stable and accurate timing with clean control signal propagation"
  - FPGA_Readiness: "💻 Design ready for hardware synthesis and deployment"

images:
  

notes:
  - "Waveforms demonstrate correct instruction execution and controlled data flow."

---

## 🧭 Future Work

planned_enhancements:
  - ⏩ Implement 5-stage or 7-stage pipelined architecture
  - ⚙️ Add hazard detection and data forwarding units
  - 🧠 Integrate instruction & data caches
  - 🔌 Deploy and test on FPGA hardware (Xilinx Artix-7)
  - 📦 Create custom RISC-V programs for complex simulations

impact:
  - "Enhancements will improve processor efficiency and bring it closer to a production-grade RISC-V core."
---



