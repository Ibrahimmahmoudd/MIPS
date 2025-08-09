# MIPS CPU Design

This repository contains the Verilog HDL implementation and supporting materials for the **VeriRISC CPU Design**, a very-reduced-instruction-set processor. The project is designed to help users understand and build a simplified processor architecture, now including a testbench for simulation.

## Overview
- **Instruction Set:** Three-bit operation code and five-bit operand, supporting eight instructions.
- **Address Space:** 32 locations.
- **Cycle Phases:** Fetch-and-execute cycle implemented in eight phases for visualization and debug (reducible to two or one with dual-port memory).
- **Inputs:** Clock (`clk`) and reset (`rst`).
- **Output:** Halt signal.
- **Test Criteria:** Pass/fail determined by the number of clock cycles consumed.

## Project Structure
- Exploring the VeriRISC CPU Design (understanding the architecture).
- Development and verification of individual components (Address Multiplexor, Counter, Controller, Register, ALU, Memory) and final verification of the complete design.

## Components
- `register_ac.v`: Accumulator register (`clk`, `rst`, `ld_ac`).
- `register_ir.v`: Instruction register (`clk`, `rst`, `ld_ir`, `alu_out`).
- `alu.v`: Arithmetic Logic Unit (`data`, `ac_out`, `opcode`).
- `counter.v`: Program counter (`clk`, `rst`, `ld_pc`, `inc_pc`).
- `mux.v`: Multiplexor (`ir_addr`, `pc_addr`, `rd`, `wr`, `ld_ir`, `ld_ac`, `ld_pc`, `inc_pc`, `halt`, `data_e`, `sel`).
- `controller.v`: Controller.
- `clk.v`: Phase generator (`clk`, `rst`, `phase`, `zero`, `alu_out`).
- `memory.v`: Memory (`addr`, `data`, `sel`, `data`, `clk`).
- `driver.v`: Data buffer.
- `risc_test.v`: Testbench file for simulating the VeriRISC CPU design.
