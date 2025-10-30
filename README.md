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

## 🧪 Testbench & Simulation

```verilog
mem[0] = 32'h00000013; // li x1, 0
mem[1] = 32'h00000113; // li x2, 0
mem[2] = 32'h002081b3; // add x3, x1, x2


