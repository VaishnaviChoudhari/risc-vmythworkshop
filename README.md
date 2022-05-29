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
    * [Introduction to Logic Gates](#Introduction-to-Logic-Gates)
    * [Basic Mux Implementation And Introduction To Makerchip](#Basic-Mux-Implementation-And-Introduction-To-Makerchip)
    * [Labs for Combinational Logic](#Labs-for-Combinational-Logic)
  * [Sequential Logic](#Sequential-Logic)
    * [Introduction To Sequential Logic And Counter Lab](#Introduction-To-Sequential-Logic-And-Counter-Lab)
    * [Sequential Calculator Lab](#Sequential-Calculator-Lab)  
  * [Pipelined Logic](#Pipelined-Logic)
    * [Pipelined Logic and Re-Timing](#Pipelined-Logic-and-Re-Timing)
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
 * If a C program is to be run on a computer or hardware which has a particular layout (Layout is the interior of the chip present in the pc). The program information needs to be pass to the computer in a certain flow. 
 * The C program is first compiled in the assembly program which is nothing but RISC V program. It is then converted into machine level language program(binary level language program). This bits are finally executed in the layout
 * An another interface is required between RISC V architecture and layout which is Hardware Description Language. RISC V Architecture is implemented in RTL code which is then implemented into layout.

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170322870-1a7b491a-695d-4390-8374-186c6777cff3.png">
</p>

### From Apps to Hardware
* Application Softwares(Apps) that runs on PC (Hardware) through a block called system software which converts application program into binary language.
* There are various layers of system software and major components are Operating System(OS), Compiler and the Assembler.
* OS handles input output operations, memory allocation and low level system functions. 
* The operating system has small functions in C, C++, java language which is converted into intructions by compiler.
* The syntax of the instructions depends on what type of hardware is. If hardware belongs to Intel x86 then the instructions will be in x86 file format which is .exe file.
* The Assembler converts these instructions into binary numbers (machine level program). This is fed to the hardware and accordingly it generates the output. 

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170328788-cbfca27f-25e9-486e-9bb7-fd9b6745080b.png">
</p>

* The instruction set acts as an abstract interface between C language and the hardware which is called as instruction set architecture of the 'architecture' of the computer.
* The RTL code is needed which understands the instructions like add. It is converted to synthesized netlist(gate level) and finally physical design implementation (layout) of the netlist is done.

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170330641-a25913ac-e8f0-4982-b5cc-7f381b867be3.png">
</p>

### Detailed Description of Course Content
Types of Instructions
1. **Pseudo Instructions** like mv(move), li(load immediate). These are simple assembly language instructions that do not have a direct machine language equivalent. During assembly, the assembler translates each psedudo- instruction into one or more machine language instructions.
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170338802-c585f039-6ecf-4b76-af11-6ec740e2aba0.png">
</p>

2. **Base Integer Instructions (RV64I)** applicable exclusively on Integers where RV stands for RISC V, 64 stands for 64 bit integer
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170339717-bee86c0f-d297-4cea-80f2-88460a9fb6ba.png">
</p>

3. **Multiply extension (RV64M)** implements multiplication and division operation.
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170341127-d2f324db-5455-4caf-bb8e-799bc231d77a.png">
</p>

4. **Single and Double Floating point extension (RV64F & RV64D)** applied to single and double point integers
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170342294-36498b04-9247-4c53-a5fe-64ff4f510c80.png">
</p>

5. **Application Binary Interface (ABI)** are the keywords which enables the application programmers to access the registers of the processor. Every keyword corresponds to RISC V  ISA
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170346064-e825090c-0938-4e13-aa27-14db76699216.png">
</p>

6. **Memory Allocation and Stack Pointer** 
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170345225-a2b41849-fc37-4316-852a-fb83ccfcb106.png">
</p>

## Labwork for RISC-V software toolchain

### C Program to compute sum from 1 to N
On Terminal, 
* Open file sum1ton.c and write C program to calculate sum of numbers from 1 to n = 5
* Compile the code using gcc command
* print output on terminal using ./a.out command

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170538536-e9d8075d-aecf-4bba-bd92-6057f353bfd0.png">
</p>

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170538907-5905d963-8bf7-4a11-9ceb-fc4da3d7dfc0.png">
</p>

### RISCV GCC compile and Disassemble

* Previously, we compiled using normal compiler, now we will compile using RISC V compiler
*  Using 'cat' command view the contents of sum1ton.c file
* In 'riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64 -o sum1ton.o sum1ton.c', we compile the code in riscv compiler where
  * mabi stands for ABI which is lp64 (long pointer 64 bits)
  * march stands for architecture which is rv64 (riscv 64)
  * 
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170545471-677c29bb-897b-4749-a577-e6b9c125ed12.png">
</p>
 
 * Using following commands goto main assembly code
   * riscv64-unknown-elf-objdump -d sum1ton.o 
   * riscv64-unknown-elf-objdump -d sum1ton.o | less
   * /main and press n

Starting address = 10184
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170549289-8dcf18f7-c67f-430f-9ea0-00cdd7684117.png">
</p>
 
* Using -Ofast instead of -O1 we get,

Starting address = 100b0
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170549820-01493107-cddf-4176-b529-d593a4e9fd29.png">
</p>

### Spike Simulation and Debug
* In this session, we will learn about debugging the program using spike -d pk sum1ton.o command where -d stands for debug
* go to program counter location at 100b0 (starting address of main.c)
* we can view the value stored in the reg using 'reg 0 reg_name' command
* Press enter to view reg value of next step

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170813960-a1a9761c-a385-48f5-8fb2-8121808ad4f4.png">
</p>

* addi is add immediate instruction
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170813991-636199a7-aafe-4971-8010-8d90c46372e0.png">
</p>




## Integer number representation
When we pass a number it is very important to understand the conversion process from decimal to binary.
### 64-bit Number System For Unsigned Numbers
64 Bit  is called as Double word
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170350763-6a3304be-fa01-4f2a-acb3-237927578e1c.png">
</p>

* ![image](https://user-images.githubusercontent.com/68154219/170351882-3d423453-9b23-4967-8a91-b1514e4b96f5.png)

 where n is the number of bits. Since the integer is of 64 bits,

* ![image](https://user-images.githubusercontent.com/68154219/170351758-5bc18604-fe98-4bae-b134-29df78da7003.png)

 which ranges from 0 to ![image](https://user-images.githubusercontent.com/68154219/170352295-93b34cc9-2a2e-4140-8344-2fbd4320ba5e.png)

 i.e, for 64 bits, range is 0 to ![image](https://user-images.githubusercontent.com/68154219/170352412-1701f152-2899-4bcf-81dd-d0038307033e.png)

 * Maximum and Minimum values for 64 bit unsigned integers are shown as below where all 1's represent maximum and all 0's represent minimum 64 bit integer in binary form.
 
 <p align="center" width="100%">
 <img src="https://user-images.githubusercontent.com/68154219/170353357-ff033ae1-1aaa-404a-b1dc-0b3907e7da66.png">
 </p>

### 64-bit Number System For Signed Numbers
* Signed Numbers, i.e, negative numbers are represented in binary form using 2's complement method.
* In 2's complement method, the number is first represented in binary form
* The binary number is inverted such that all 0's are replaced by 1's and vice versa (1's complement)
* Add 1 to the inverted binary number to get 2's complement
* **POSITIVE NUMBERS HAS MSB '0' AND NEGATIVE NUMBERS HAS MSB '1'

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170526180-c0701299-9062-4ab6-9cd9-08e79506ee18.png">
</p>

* Range of Signed Positive Numbers is '0' to ' ![image](https://user-images.githubusercontent.com/68154219/170526968-f1b5f9ed-2b91-43e4-a71b-afb16cf54297.png) ' where n is no. of bits which is 64 bits

* Range of Signed Negative Numbers is '-1' to ' ![image](https://user-images.githubusercontent.com/68154219/170528164-a960eb9f-ad61-448d-8122-c21f4af368eb.png) ' where n is no. of bits which is 64 bits

### Lab for Signed and Unsigned Numbers
* **Lab to find Highest unsigned integer input value**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170817817-dda818c0-c08b-4680-a29d-9b4dc340d0d2.png">
</p>

* **For unsigned long long datatype with input value greater than 64**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170817283-ece27286-cdf9-49c2-8b2f-e39245cc4c53.png">
</p>

Since unsigned long long dataytpe has max size of 64 bits, Highest size of output remains same even if the input value is greater than 64 bits

* **For unsigned long long datatype with input value less than 64**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170817568-87321d45-3d6e-49db-a80b-715a0c51148a.png">
</p>

* **For unsigned long long datatype with negative input value** 
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170817646-95ac26c7-a683-4b24-a171-2e6b2f2ef972.png">
</p>

* **Highest and lowest value for signed long long integer input value**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170817696-bbafdf40-5821-4065-8ddf-b987afae06fd.png">
</p>
 
 
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170817899-3298107d-cfd4-46d1-9ae4-234c00e82f5d.png">
</p>

 # Day 2: Introduction to ABI and basic verification flow
 ***
 ## Application Binary Interface
 ### Introduction to Application Binary Interface
 
 In RISC V program, the ABI are as shown in the snippet below
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170822448-8b4dfbd7-578a-4491-9ed6-8943772a1bdb.png">
</p>


 * For users, the interface is the appearance and functionality of the application
 * The interface in the applicagtion program uses a lot of standard libraries such as stdio.h, etc. in C, std:array, etc. in C++  which are called as Application program interface
 * The next lower layer is the Operating system. The Application program can access the operating system via standard libraries and the interface.
 * Similarly, the operating system can access the machine level program via ISA interface which can be RISC V or ARM or any other architechture
 * This architechture is implemented on the hardware using RTL interface
 * Some parts of the ISA are available to the user called as USER ISA while some parts of the ISA are available for operating system called as USER & SYSTEM ISA
 * The application can access the registers (Hardware resources) of the architechture via system calls and this particular interface is called as **Application Binary Interface (ABI)**
 * **64 bits(XLEN) RISC V has 32 registers**
 <p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170823132-a929ca44-09be-48f3-a3c7-d1d81aa81bf6.png">
</p>

### Memory Allocation for Double Words

* RISC V belongs to 'Little Endian'memory addressing system. LSB of data stored at 0th location of the register.
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170824092-2819ae17-35b9-4a88-975a-71b1c067b5bc.png">
</p>

There are two ways of loading data into register
* First method is to load data directly into 64 bit register 
* Second method is loading data into register through the memory 
* Loading through memory has 1 byte of address at each memory location
* If Address of 1st doubleword is m[0] then address of 2nd doubleword is m[8], 3rd doubleowrd is m[16] and so on.

### Load, Add And Store Instructions With Example

For Example,
* Assume that the array M is of 3 double word (data to be stored)
* We want to store the content in a particular register, let's say register x8.
* If we want to access the data from register x8 through memory, we need the first memmory address of the register.
* x23 will store the base address of array M. and the pointer is incremented by 16 from base address(offset as shown in the snippet, memory address starts from 16 to 23).
* **load double word (ld)** is the command to load the data into the register x8.

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170826147-c9be50d9-90f0-46f0-a3a3-0b339770d289.png">
</p>


 **All the instructions in RISC V are of 32 bits.**
* opcode - first 7 bits are used to store commands 
* func3 - additional 3 bits along with opcode
* rs1 - 5 bits used to store source register
* rd- 5 bits used to store destination register
* immediate - offset from base address of the register

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170826093-5307b4d3-dc34-42d0-a6e9-ca1df48e7ff9.png">
</p>

* To store the data back into memory, **store double word sd** command is used.
* Then for example, x8 is the data register and x23 is the source register with offset 8 ( in snippet the memory address starts from 8 to 15)
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170825689-bdb1b858-ef29-47a0-a837-1c8a48ea0f8c.png">
</p>

The instruction set for addition and storing data back to memory is as shown in the snippet below
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170825850-6a7b8c44-005f-4d76-ac31-e532b4aa09cb.png">
</p>

* There are two source register for add command 
* There is no destination register for sd command but there are two registers as source and data.

### Concluding 32-registers And Their Respective ABI Names
* The instruction ld, add, sd belongs to Base Integer Instructions RV64I 
* The instructions such as add which operates only on registers are called as R-type instructions.
* The instructions that operate on registers and immediate are called as I- type instructions.
* The instructions that operate on source registers and immediate are called as S-type instructions.
* All registers are of 5 bitswhich represents 32 registers.
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170829577-48980b55-4a64-4fba-9786-38ed96de0df6.png">
</p>

## Labwork using ABI function calls
### Study New Algorithm For Sum 1 to N Using ASM

In this lab we will pass two registers a0, a1 from Main C program to ASM and return the output in a0 register back to the Main C program
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170830186-ab84ce27-6e5a-4b7d-9a6b-ab72022919af.png">
</p>

Following is the algorithm for the program in ASM

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170830005-5fa913b7-2334-405d-8757-65ffb7070447.png">
</p>

### Review ASM Function Call
On terminal open leafpad
* Type Main C program with load as an extern function
* Type assembly program for load function

![image](https://user-images.githubusercontent.com/68154219/170831347-b12fa86f-0d0c-4525-980b-99c0ee479800.png)

![image](https://user-images.githubusercontent.com/68154219/170831368-c5d3dbe9-ab4e-4136-b0f7-fd15bf6b995c.png)

![image](https://user-images.githubusercontent.com/68154219/170831473-f21d1b0b-3619-4e0e-8a40-926f52e16a66.png)

### Simulate New C Program With Function Call
Int this section we will simulate the program with spike command for RISC V simulation

![image](https://user-images.githubusercontent.com/68154219/170832645-50953dca-3622-4ded-b82f-4061f5005fbf.png)

![image](https://user-images.githubusercontent.com/68154219/170832690-810775ab-ca1f-466d-8514-5f4c6f5219d5.png)

## Basic verification flow using iverilog
### Lab To Run C-Program On RISC-V CPU

In this lab, we will load hex file of C program in Memory and we will read the memory through the RISCV CPU . The CPU willprocess the hex file and display the output.
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170833527-3522cd08-e4ee-4324-821a-7e8cebf1f5d0.png">
</p>

* In testbench file, following line loads hex file (firmware.hex) in RISC V CPU and generates bitstream file(firmware32.hex)
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170839545-c6cf683c-0ba7-467f-b3ec-afd17d19ad0e.png">
</p>

* rv32im.sh file converts the C program into hex file
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170839608-232f678c-09d7-481a-8368-72f5c3f43259.png">
</p>

* ./rv32im.sh displays the output on the terminal
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170839608-232f678c-09d7-481a-8368-72f5c3f43259.png">
</p>

* firmware.hex looks like as shown in the snippet below
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170839721-49172654-433d-4c77-893e-5ad143d682fe.png">
</p>

* firmware32.hex file is the output bitsteam file which is as below
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170839762-18121b6d-49b1-445f-aa19-bf72e53ed0dc.png">
</p>

On terminal,
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170839816-f7be93e5-b2f7-46c0-8bf1-bad2b6c10a8e.png">
</p>

# Day 3: Digital Logic with TL-Verilog and Makerchip
***
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170840097-d5f5cb94-2f7f-45e4-b72a-a07397c92add.png">
</p>

* [TL-Verilog](https://arxiv.org/abs/1811.01780) 
Transaction-Level Verilog (TL-Verilog) is an emerging extension to SystemVerilog that supports a new design methodology, called transaction-level design. A transaction, in this methodology, is an entity that moves through structures like pipelines, arbiters, and queues, A transaction might be a machine instruction, a flit of a packet, or a memory read/write. Transaction logic, like packet header decode or instruction execution, that operates on the transaction can be placed anywhere along the transaction's flow. Tools produce the logic to carry signals through their flows to stitch the transaction logic.

* [Makerchip IDE](http://makerchip.com/)
It is a platform that provides provides free and instant access to the latest tools directly from your browser and from your desktop. This includes open-source tools and proprietary ones

## Combinational Logic with TL-Verilog and Makerchip
### Introduction to Logic Gates

* Basic Logic Gates are:
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170840593-5e31e005-dd44-4455-a6df-84f955235d09.png">
</p>

* Combinational Circuit for example, Full Adder
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170840690-30eef614-a670-44e2-808b-ff7f3a7ecc0f.png">
</p>

Multiple Bits addition using sequence of Full Adders
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170840805-a06d51a1-742e-4674-8d39-2d776af84d8a.png">
</p>

* Boolean Equations of Logic Gates
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170840856-7214ecd7-5f94-47dd-bc4f-fc3de84f782a.png">
</p>

### Basic Mux Implementation And Introduction To Makerchip

The basic builing block of digital circuit is Multiplexer(MUX)
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170840934-1be1be57-84f4-4ee5-8a35-46a1bf0ab161.png">
</p>

* **Chaining Ternary Operator**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170841024-f600c940-0228-4700-9ae8-ded8d6ccdb19.png">
</p>

### Labs For Combinational Logic

Open Pythagorean example from Tutorial
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170841452-b2800511-8836-42cb-8184-fc999c29d107.png">
</p>

**A. Inverter** 
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170841651-a265df72-02fb-4b56-93d6-29003532f6fa.png">
</p>

**B. 2 Input AND gate**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170841711-e08a0d5f-f983-4e9d-bc29-93e253a30364.png">
</p>

**C. Arithmetic operators on vectors as binary numbers**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170841789-458c1892-3e59-49c3-8ff8-205c14bff58b.png">
</p>

**D. MUX**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170842066-7d953eb1-836f-4425-81b9-26e5f3f599dc.png">
</p>

**E. MUX as Vector**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170842028-af722b1a-041a-4993-8ec9-2b226000590b.png">
</p>

**D. Combinational Calculator**

[Makerchip IDE](https://www.makerchip.com/sandbox/00Rf2hWvg/0wjhG7D)
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170842548-6c41c075-c8ea-405e-88cb-9c305f4bd52a.png">
</p>

## Sequential Logic
### Introduction To Sequential Logic And Counter Lab
* The whole sequential circuit can be viewed as a big state machine
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170842751-c58ffb0d-0c11-4f36-bb3f-c1218f8ba9db.png">
</p>

* **Sequential Logic - Fibonacci Series**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170842839-e8de66a4-70dd-4763-b70e-e5b2abae0c15.png">
</p>

* **Fibonacci Series - Reset**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170842984-032dc0d4-7337-4678-bc17-3a38f27b0d71.png">
</p>

* **Free Running counter**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170843343-a926d3fa-fb38-493e-ae7c-837ed0124b70.png">
</p>

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170843310-6b443cab-a028-406f-95dd-c716f2b3edee.png">
</p>

* **Fibonacci Series**

[Makerchip IDE](https://www.makerchip.com/sandbox/00Rf2hWvg/0Vmhxwn#)
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170843434-87f215e7-873f-4336-a075-5ce21edf2acd.png">
</p>

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170843425-c5a35c4c-a755-4f3b-8078-537321fb63b3.png">
</p>

### Sequential Calculator Lab
[Makerchip IDE](https://www.makerchip.com/sandbox/00Rf2hWvg/0y8hrg4)
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170844256-0be20bb6-59ec-4567-bf84-b89f728bcc67.png">
</p>

## Pipelined Logic 

### Pipelined Logic and Re-Timing

* **Compute Pythagoras Theorem on hardware**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170844353-e7afc255-eb88-441c-ae26-a4699a085388.png">
</p>

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170844382-06acccb3-9a80-45b5-aaea-f82038d4553b.png">
</p>

* **TL-Verilog vs System Verilog**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170844460-05055a6c-4bf3-4959-82cb-333e0dc35771.png">
</p>

* **Retiming - Easy and Safe**
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170844553-327d637d-59c8-46de-a1d5-e9bb4246c92e.png">
</p>

### Pipeline Logic Advantages And Demo In Platform

* **High Frequency**
When clock is fast, using pipelining we are able to run on high frequency.

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170859988-cb0bb3ee-7198-4c30-adb7-29cb1ce44ecb.png">
</p>

For example, Pythagoras Theorem with Pipeline
[Makerchip IDE](https://www.makerchip.com/sandbox/00Rf2hWvg/0wjhG7D)
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170860434-1557ef57-7a48-4a29-a234-ab078b4c5dfb.png">
</p>

It can be seen that the input 'a' is squared after first clock cycle, input 'b' is squared after second clock cycle and output 'c' is generated after 3 clock cycles.

Without pipeline,
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170860582-aab65a8d-a5d0-46f7-a92b-e00766374827.png">
</p>

It can be seen that the input 'a' and input 'b' are squared after third clock cycle and output 'c' is also generated after 3 clock cycles.

### Lab On Error Conditions Within Computation Pipeline

* **Identifiers and Types**

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170861999-8e0e91ed-9c20-4a95-9c2d-4b41d08af416.png">
</p>

**Lab: Pipeline**
[Makerchip IDE](https://www.makerchip.com/sandbox/00Rf2hWvg/0GZh1mk)
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/170864596-f8137f62-18dc-4b84-98fd-68be92b898d1.png">
</p>

### Lab On 2-Cycle Calculator

**Lab: Counter and Calculator in Pipeline**




























