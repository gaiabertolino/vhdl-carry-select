# 16-bit Carry-Select Adder Design and Verification

#### Keywords

`Digital Electronics`, `Combinational Circuits`, `Carry-Select Adder`, `Ripple-Carry Adder`, `Full Adder`, `Multiplexer`, `VHDL`, `FPGA`, `Vivado`, `Timing Analysis`, `Power Analysis`.

This project focuses on the **design, implementation, and verification of a 16-bit Carry-Select Adder (CSA)**, a high-performance combinational arithmetic circuit aimed at reducing propagation delay compared to traditional ripple-carry adders.

The adder is described in **VHDL**, simulated at multiple abstraction levels, and synthesized for FPGA implementation. The project highlights the trade-off between **speed improvement** and **hardware redundancy**, demonstrating how parallel computation and selection logic can significantly reduce critical path delay.

This project was developed as part of the coursework exam for the *Digital Electronics* course during the academic year **2021/2022**. 

---

### Key Features

* **High-Speed Addition**: Reduced carry propagation delay through parallel computation.
* **Parametric Design**: Generic-based VHDL implementation enabling scalability.
* **Hierarchical Architecture**: Modular construction using full adders, ripple-carry adders, and multiplexers.
* **Comprehensive Verification**: Exhaustive testbench and multi-stage simulation.
* **FPGA-Oriented Analysis**: Timing and power evaluation after synthesis and implementation.

---

### Project Structure

* **Full Adder**

  * Fundamental building block implemented using two half adders
  * Computes sum and carry with support for input carry (`Cin`)

* **Multiplexer**

  * Selects the correct precomputed sum and carry based on the incoming carry signal
  * Implemented in VHDL using IEEE `std_logic` types

* **Ripple-Carry Adder (RCA)**

  * Parametric module composed of cascaded full adders
  * Used as the base computation unit within each CSA block

* **Carry-Select Adder (16-bit)**

  * Symmetric architecture composed of three 8-bit ripple-carry adders
  * Parallel computation of partial sums assuming carry-in equal to 0 and 1
  * Selection logic implemented via multiplexers
  * Final full adder manages signed overflow

* **Testbench**

  * Initial functional test using signed operands
  * **Exhaustive simulation** covering all possible 16-bit input combinations
  * Automatic error detection by comparing hardware output with algebraic sum

---

### Simulation and Validation

* **Behavioral Simulation**

  * Functional correctness verified with zero error across all input combinations

* **Post-Synthesis Timing Simulation**

  * Analysis of propagation delays introduced by logic elements

* **Post-Implementation Simulation**

  * FPGA-level behavior analysis, including LUT utilization and routing effects
  * Observation of realistic timing behavior and periodic delay-induced artifacts

---

### Performance Analysis

* **Critical Path Analysis**: Evaluation of gate delays in ripple-carry vs carry-select structures
* **Timing Results**:

  * Post-synthesis delay: ~3.67 ns
  * Post-implementation delay: ~6.38 ns
* **Power Consumption**:

  * Dynamic power ≈ 91%
  * Static power ≈ 9%

---

### Report

* **Technical Report (Italian)**:

  * Formal explanation of carry-select architecture and design rationale
  * VHDL entity and architecture descriptions
  * RTL, post-synthesis, and post-implementation analysis
  * Timing, power consumption, and hardware efficiency discussion
