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
    * [Basic Mux Implementation And Introduction To Makerchip](#Basic-Mux-Implementation-And-Introduction-To-Makerchip)
    * [Labs for Combinational Logic](#Labs-for-Combinational-Logic)
  * [Sequential Logic](#Sequential-Logic)
    * [Introduction To Sequential Logic And Counter Lab](#Introduction-To-Sequential-Logic-And-Counter-Lab)
    * [Sequential Calculator Lab](#Sequential-Calculator-Lab)  
  * [Pipelined Logic](#Pipelined-Logic)
    * [Pipelined Logic and Re-Timing](#[Pipelined-Logic-and-Re-Timing)
    * [Pipeline Logic Advantages And Demo In Platform](#Pipeline-Logic-Advantages-And-Demo-In-Platform)
    * [Lab On Error Conditions Within Computation Pipeline](#Lab-On-Error-Conditions-Within-Computation-Pipeline)
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
  * [Introduction to Simple RISC-V Micro-architecture](#Introduction-to-Simple-RISC-V-Micro-architecture)
    * [Micro-architecture-of-Single-Cycle-RISC-V-CPU](#Micro-architecture-of-Single-Cycle-RISC-V-CPU)
    * [Starting Point Code for RISC-V Labs Part-1](#Starting-Point-Code-for-RISC-V-Labs-Part-1)
    * [Starting Point Code for RISC-V Labs Part-2](#Starting-Point-Code-for-RISC-V-Labs-Part-2)  
  * [Fetch and Decode](#Fetch-and-Decode)
    * [Implementation Plan and Lab for PC](#Implementation-Plan-and-Lab-for-PC)
    * [Lab For Instruction Fetch Logic](#Lab-For-Instruction-Fetch-Logic)
    * [Lab For RV Instruction Types IRSBJU Decode Logic ](#Lab-For-RV-Instruction-Types-IRSBJU-Decode-Logic)
    * [Lab For Instruction Immediate Decode Logic For RV-ISBUJ ](#Lab-For-Instruction-Immediate-Decode-Logic-For-RV-ISBUJ)
    * [Lab To Decode other Fields of Instructions For RV-ISBUJ](#Lab-To-Decode-other-Fields-of-Instructions-For-RV-ISBUJ)
    * [Lab To Decode Instruction Field Based on Instr Type RV-ISBUJ](#Lab-To-Decode-Instruction-Field-Based-on-Instr-Type-RV-ISBUJ)
    * [Lab To Decode Individual Instruction](#Lab-To-Decode-Individual-Instruction)
  * [RISC-V control logic](#RISC-V-control-logic)
    * [Lab For Register File Read Part1 (USE UPDATED SHELL CODE) ](#Lab-For-Register-File-Read-Part-1-USE-UPDATED-SHELL-CODE)  
    * [Lab For Register File Read Part-2 ](#Lab-For-Register-File-Read-Part-2)
    * [Lab For ALU Operations For add/addi ](#Lab-For-ALU-Operations-For-add-addi)
    * [Lab For Register File Write](#Lab-For-Register-File-Write)
    * [Concept of Array And Register File Details](#Concept-of-Array-And-Register-File-Details)
    * [Lab For Implementing Branch Instructions ](#Lab-For-Implementing-Branch-Instructions)
    * [Lab For Completing Branch Instruction Implementation](#Lab-For-Completing-Branch-Instruction-Implementation)
***
* [Day 5: Complete Pipelined RISC-V CPU micro-architecture](#Day-5-Complete-Pipelined-RISC-V-CPU-micro-architecture)
  * [Pipelining the CPU ](#Pipelining-the-CPU)
    * [Introduction To Control Flow Hazard And Read After Write Hazard](#Introduction-To-Control-Flow-Hazard-And-Read-After-Write-Hazard) 
    * [Lab To Create 3-Cycle Valid Signal](#Lab-To-Create-3-Cycle-Valid-Signal)
    * [Lab To Code 3-Cycle RISC-V To Take Care Of Invalid Cycles](#Lab-To-Code-3-Cycle-RISC-V-To-Take-Care-Of-Invalid-Cycles)
    * [Lab To Modify 3-Cycle RISC-V To Distribute Logic](#Lab-To-Modify-3-Cycle-RISC-V-To-Distribute-Logic)
  * [Solutions to Pipeline Hazards ](#Solutions-to-Pipeline-Hazards)
    * [Lab For Register File Bypass To Address Rd-After-Wr Hazard](#Lab-For-Register-File-Bypass-To-Address-Rd-After-Wr-Hazard)
    * [Lab For Branches To Correct The Branch Target Path](#Lab-For-Branches-To-Correct-The-Branch-Target-Path)
    * [Lab To Complete Instruction Decode Except Fence, Ecall, Ebreak](#Lab-To-Complete-Instruction-Decode-Except-Fence-Ecall-Ebreak)
    * [Lab To Code Complete ALU ](#Lab-To-Code-Complete-ALU)
  * [Load/Store Instructions and Completing RISC-V CPU](#Load-Store-Instructions-and-Completing-RISC-V-CPU)
    * [Introduction To Load Store Instructions And Lab To Redirect Loads](#Introduction-To-Load-Store-Instructions-And-Lab-To-Redirect-Loads)
    * [Lab To Load Data From Memory To Register File](#Lab-To-Load-Data-From-Memory-To-Register-File)
    * [Lab To Instantiate Data Memory To The CPU](#Lab-To-Instantiate-Data-Memory-To-The-CPU)
    * [Lab To Add Stores And Loads To The Test Program](#Lab-To-Add-Stores-And-Loads-To-The-Test-Program)
    * [Lab To Add Control Logic For Jump Instructions](#Lab-To-Add-Control-Logic-For-Jump-Instructions)
    * [Wrap Up](#Wrap-Up)
 ***
    
 # Day 1: Introduction to RISC-V ISA and GNU compiler toolchain
 ***
 ## Introduction to RISC-V basic keywords
 #### RISC V Instruction Set Architechture (ISA)
 * An Instruction Set Architecture or ISA is an abstract model of a computer architecture, defining such things as the register model and machine code instructions.
 * A realization of an ISA, such as a Central Processing Unit (CPU), is called an implementation. Widely used ISAs include x86 and ARM.
 * ISAs are intellectual property that is licensed. So, for example, a manufacturer like Freescale or Broadcom that wishes to design an ARM-compatible processor needs to license it from Arm Ltd., the owners of the ISA.
 * RISC-V pronounced "risk-five," RISC-V is an ISA based on reduced instruction set computer (RISC) principles. Unlike most other ISA designs, it is provided under a open source license that does not require fees to use.
 * RISC-V is significant because it will allow smaller device manufacturers to build hardware without paying royalties and allow developers and researchers to design and experiment with a proven and freely available instruction set architecture. This will encourage innovation and competition 
 
 ### Introduction
 * If a C program is to be run on a computer or hardware which has a particular layout (Layout is the interior of the chip present in the pc). The C program information needs to be pass to the computer in a certain flow. 
 * The C program is first compiled in the assembly program which is nothing but RISC V program. It is then converted into machine level language program(binary level language program). This bits are finally executed in the layout
 * An another interface is required between RISC V architecture and layout which is Hardware Description Language. RISC V Architecture is implemented in RTL code which is then implemented into layout.

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170322870-1a7b491a-695d-4390-8374-186c6777cff3.png">
</p>




