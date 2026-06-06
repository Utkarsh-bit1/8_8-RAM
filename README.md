# 8x8 Synchronous RAM in Verilog

## 📌 Project Overview
This repository contains a fully synthesizable **8x8 Synchronous Single-Port RAM** design implemented in Verilog HDL. The module supports stable clock-driven read and write operations,
features an active-high asynchronous reset to clear memory contents, and implements structural priority logic to prevent resource contention. 

This project was built independently over my 1st-year summer vacation to master RTL design, hardware priority rules, and validation workflows using simulation testbenches.

## 🛠️ Tech Stack & Tools
- **Language:** Verilog HDL
- **IDE & Simulator:** Xilinx Vivado 
- **Methodology:** Register Transfer Level (RTL) Design & Behavioral Modeling

## ⚙️ Hardware Specifications
- **Memory Depth:** 8 addresses (`[2:0]`)
- **Data Width:** 8 bits per location (`[7:0]`)
- **Memory Size:** 64 bits total storage array ( reg [7:0] memory [7:0] )
- **Control Signal Priority:** Asynchronous Reset ( rst ) has absolute priority over Write Enable ( w_enb ).

## 🧪 Simulation & Verification
The verification environment ( RAM_8_8_test.v ) evaluates the hardware logic through a structured stimulus sequence:
1. **Reset Phase:** Asserts 'rst' to initialize all internal memory locations to '8'b0'.
2. **Write Cycle:** Sets 'w_enb = 1' and sequentially writes distinct 8-bit binary patterns to memory slots.
3. **Read Cycle:** Drops 'w_enb = 0' to verify data retention by sequentially reading back the stored contents.


