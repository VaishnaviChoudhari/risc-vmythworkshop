# RISC-V based MYTH Workshop
[![risc-vMythWorkshopLOGO](https://osfpga.org/wp-content/uploads/2022/05/Cloud-based-RISC-V-on-FPGA-and-OpenFPGA-5.png)](https://osfpga.org/osfpga-training/)

## Brief Description of the Workshop
A beginner level 5-day workshop on “RISC-V based MYTH” in which by end of the workshop we will understand:
 * RISC-V specs basics
 * RISC-V software basics
 * How to implement RISC-V basic specs using TL-Verilog
 * Simulate your own RISC-V core

# *Index*
***
* [Day 1: Introduction to RISC-V ISA and GNU compiler toolchain](#Day-1-Introduction-to-RISC-V-ISA-and-GNU-compiler-toolchain)
  * [Introduction to RISC-V basic keywords](#Introduction-to-RISC-V-basic-keywords)
    * [Introduction](#Introduction)
    * [From Apps to Hardware](#From-Apps-to-Hardware)
    * [Detailed Description of Course Content](#Detailed-Description-of-Course-Content)
  * [Labwork for RISC-V software toolchain](#Labwork-for-RISC-V-software-toolchain)
    * [C Program to compute sum from 1 to N](#C-Program-to-compute-sum-from-1-to-N)
    * [RISCV GCC compile and Disassemble](#RISCV-GCC-compile-and-Disassemble)
    * [Spike Simulation and Debug](#Spike-Simulation-and-Debug)
  * [Integer number representation](#Integer-number-representation)
    * [64-bit Number System For Unsigned Numbers](#64-bit-Number-System-For-Unsigned-Numbers) 
    * [64-bit Number System For Signed Numbers](#64-bit-Number-System-For-Signed-Numbers)
    * [Lab for Signed and Unsigned Numbers](#Lab-for-Signed-and-Unsigned-Numbers)
***
* [Day 2: Introduction to ABI and basic verification flow](#Day-2-Introduction-to-ABI-and-basic-verification-flow)
  * [Application Binary Interface](#Application-Binary-Interface)
    * [Introduction to Application Binary Interface](#Introduction-to-Application-Binary-Interface)
    * [Memory Allocation for Double Words](#Memory-Allocation-for-Double-Words)
    * [Load, Add And Store Instructions With Example](#Load-Add-And-Store-Instructions-With-Example)
    * [Concluding 32-registers And Their Respective ABI Names](#Concluding-32-registers-And-Their-Respective-ABI-Names)
  * [Labwork using ABI function calls](#Labwork-using-ABI-function-calls)
    * [Study New Algorithm For Sum 1 to N Using ASM](#Study-New-Algorithm-For-Sum-1-to-N-Using-ASM)
    * [Review ASM Function Call](#Review-ASM-Function-Call)
    * [Simulate New C Program With Function Call](#Simulate-New-C-Program-With-Function-Call)
  * [Basic verification flow using iverilog](#Basic-verification-flow-using-iverilog)
    * [Lab To Run C-Program On RISC-V CPU](#Lab-To-Run-C-Program-On-RISC-V-CPU)
***
* [Day 3: Digital Logic with TL-Verilog and Makerchip](#Day-3-Digital-Logic-with-TL-Verilog-and-Makerchip)
  * [Combinational Logic with TL-Verilog and Makerchip](#Combinational-Logic-with-TL-Verilog-and-Makerchip)
    * [Welcome](#Welcome) 
    * [Introduction to Logic Gates](#Introduction-to-Logic-Gates)
    * [Basic Mux Implementation And Introduction To Makerchip](#Basic Mux Implementation And Introduction To Makerchip)
    * [Labs for Combinational Logic](#Labs-for-Combinational-Logic)
  * [Sequential Logic](#Sequential-Logic)
    * [Introduction To Sequential Logic And Counter Lab](#Introduction To Sequential Logic And Counter Lab)
    * [Sequential Calculator Lab](#Sequential-Calculator-Lab)  
  * [Pipelined Logic](#Pipelined-Logic)
    * [Pipelined Logic and Re-Timing](#[Pipelined-Logic-and-Re-Timing)
    * [Pipeline Logic Advantages And Demo In Platform](#Pipeline-Logic-Advantages-And-Demo-In-Platform)
    * [Lab On Error Conditions Within Computation Pipeline](#Lab-On Error-Conditions-Within-Computation-Pipeline)
    * [Lab On 2-Cycle Calculator ](#Lab-On-2-Cycle-Calculator)
  * [Validity](#Validity)
    * [Introduction To Validity And Its Advantages](#Introduction-To-Validity-And-Its-Advantages)
    * [Lab On Validity And Valid When Condition](#Lab-On-Validity-And-Valid-When-Condition)
    * [Lab To Compute Total Distance](#Lab-To-Compute-Total-Distance)
    * [Lab on 2-cycle Calculator with Validity](#Lab-on-2-cycle-Calculator-with-Validity)
    * [Calulator-Single-Value-Memory-Lab](#Calulator-Single-Value-MemoryLab)
  * [Wrap-Up](#Wrap-Up)
    * [(Bonus)Introduction To Hierarchy Concept](#Bonus-Introduction-To-Hierarchy-Concept)
***
* [Day 4: Basic RISC-V CPU micro-architecture](#Day-4-Basic-RISC-V-CPU-micro-architecture)
  * [Introduction to Simple RISC-V Micro-architecture](#Introduction to Simple RISC-V Micro-architecture)
    * [Micro-architecture-of-Single-Cycle-RISC-V-CPU](#Micro-architecture-of-Single-Cycle-RISC-V-CPU)
    * [Starting Point Code for RISC-V Labs Part-1](#Starting-Point-Code-for-RISC-V-Labs Part-1)
    * [Starting Point Code for RISC-V Labs Part-2](#Starting-Point-Code-for-RISC-V-Labs Part-2)  
  * [Fetch and Decode](#Fetch-and-Decode)
    * [Implementation Plan and Lab for PC](#Implementation-Plan-and-Lab-for-PC)
    * [Lab For Instruction Fetch Logic](#Lab-For-Instruction-Fetch-Logic)
    * [Lab For RV Instruction Types IRSBJU Decode Logic ](#Lab-For-RV-Instruction-Types-IRSBJU-Decode-Logic)
    * [Lab For Instruction Immediate Decode Logic For RV-ISBUJ ](#Lab-For-Instruction-Immediate-Decode-Logic-For-RV-ISBUJ)
    * [Lab To Decode other Fields of Instructions For RV-ISBUJ](#Lab-To-Decode-other-Fields-of-Instructions-For-RV-ISBUJ)
    * [Lab To Decode Instruction Field Based on Instr Type RV-ISBUJ](#Lab-To-Decode-Instruction-Field-Based-on-Instr-Type-RV-ISBUJ)
    * [Lab To Decode Individual Instruction](#Lab-To-Decode-Individual-Instruction)
  * [RISC-V control logic](#RISC-V-control-logic)
  * [Lab Synth sim mismatch blocking statement ](#Lab-Synth-sim-mismatch-blocking-statement)
***
* [Day 5: If, case, for loop and for generate](#Day-5-If-case-for-loop-and-for-generate)
  * [If Case Constructs](#If-Case-Constructs)
  * [Labs on Incomplete IF Case](#Labs-on-Incomplete-IF-Case)
  * [Labs on Incomplete Overlappin Case](#Labs-on-Incomplete-IF-Case)
 ***
    
 # Day 1: Introduction to Verilog RTL Design and Synthesis
 ***
 ## Introduction to open-source simulator iverilog
