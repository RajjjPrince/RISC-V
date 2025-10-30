# 🧠 RISC-V Processor Implementation  

A **Verilog-based RISC-V processor** design and simulation project using **Xilinx Vivado**.

---

## 🏷️ Badges

![Language](https://img.shields.io/badge/Language-Verilog-blue.svg)
![Tool](https://img.shields.io/badge/Tool-Xilinx%20Vivado-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

---

## 📘 Overview

This project implements a **32-bit RISC-V processor** based on the **RV32I** instruction-set architecture.  
It is designed, synthesized, and simulated in **Verilog HDL** using **Xilinx Vivado 2023.x**.

---

## ⚙️ Key Features

- ✅ Implements **RV32I core instruction set**  
- ⚡ Supports arithmetic, logic, and branch operations  
- 🧩 Five pipeline stages — **Fetch | Decode | Execute | Memory | Writeback**  
- 💡 Modular Verilog HDL design  
- 🧪 Fully **testbench-verified**  
- 🔧 Synthesizable for **FPGA deployment**

---


---

## 🧪 Testbench & Simulation

The Verilog **testbench** verifies the processor by:
- Initializing instruction memory with machine codes  
- Monitoring register and memory outputs  
- Checking correctness of executed instructions  

### 🧾 Example Test Program (Machine Code)

```verilog
mem[0] = 32'h00000013; // li x1, 0
mem[1] = 32'h00000113; // li x2, 0
mem[2] = 32'h002081b3; // add x3, x1, x2


```
📊 Block Diagram
<p align="center"> <img src="Screenshots/Screenshot 2025-10-30 135937.png" alt="Block Diagram" width="100%"> </p>


📷 Simulation Output

<p align="center"> <img src="Screenshots/Screenshot 2025-10-30 142436.png" alt="Block Diagram" width="100%"> </p>

## 🧮 Tools & Environment

| Tool                   | Version         | Usage                             |
| ---------------------- | --------------- | --------------------------------- |
| **Xilinx Vivado**      | 2023.x or later | Design, synthesis, and simulation |
| **Verilog HDL**        | IEEE-1364       | Processor design                  |
| **ModelSim / GTKWave** | Optional        | Waveform visualization            |
| **GitHub**             | —               | Version control & documentation   |

## 🚀 How to Run

```# 1. Clone the repository
git clone https://github.com/<your-username>/riscv-processor.git
cd riscv-processor

# 2. Open the project in Xilinx Vivado
# 3. Add all .v source files and the testbench
# 4. Run behavioral simulation
# 5. View results in the waveform viewer
```
## 📂 Project Structure
```riscv-processor/
│
├── src/                     # Verilog source files
│   ├── alu.v
│   ├── control_unit.v
│   ├── register_file.v
│   └── ...
│
├── sim/                     # Testbench and simulation files
│   └── tb_riscv.v
│
├── screenshots/              # Add block diagrams & simulation results here
│   ├── screenshots
│
├── README.md
└── LICENSE (optional)
```

## 📈 Results

✅ Successfully implemented and simulated 32-bit RISC-V processor

🧠 Verified arithmetic, logic, and branch instruction correctness

⚙️ Generated stable timing and control waveforms

💻 Ready for FPGA synthesis and extension with pipelined architecture

## 🧭 Future Work

⏩ Add 5-stage or 7-stage pipelining

⚙️ Implement hazard detection and forwarding unit

🧠 Integrate instruction & data cache

🔌 Deploy on FPGA (e.g., Xilinx Artix-7)

## 👨‍💻 Author


---

## 👨‍💻 Author

**Prince Raj**  
📧 [princerajsonepur@gmail.com](mailto:princerajsonepur@gmail.com)

🔗 **Connect With Me:**
- [LinkedIn](https://www.linkedin.com/in/https://www.linkedin.com/in/prince-raj-966ba3269//)
- [GitHub](https://github.com/https://github.com/RajjjPrince/RISC-V)
