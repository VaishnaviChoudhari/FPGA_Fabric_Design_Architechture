# FPGA_Fabric_Design_Architechture

[![risc-vMythWorkshopLOGO](https://osfpga.org/wp-content/uploads/2022/05/Cloud-based-RISC-V-on-FPGA-and-OpenFPGA-5.png)](https://osfpga.org/osfpga-training/)

## Brief Description of the Workshop
June 1st – June 5th

In this workshop, we broadly cover 5 modules. The first module focuses on taking a digital design through Xilinx Vivado and programming it on the FPGA. We also demonstrate area, timing analysis, and post-implementation simulation. In the second module, we describe the OpenFPGA framework and demonstrate the VTR tool flow on two designs with an example architecture. Next, we repeat these tasks for a RISC-V based processor called RVMyth. We simulate RVMyth with a testbench through Vivado and program it on a Basys3 board. We then take it through the OpenFPGA framework through Skywater OpenSource FPGA (SOFA). We also demonstrate area, timing analysis, and post implementation simulation for the processor core after taking it through SOFA. Lastly, we summarize the area and timing results obtained by the design from Basys3 and VTR.

# *Index*
***
* [Day 1: ](#Day-1)
  * [FPGA Introduction](FPGA-Introduction)
    * [What Is FPGA And FPGA Architecture?](#What-Is-FPGA-And-FPGA-Architecture)
    * [Look-up Tables, FPGA Programming And Design Methodology](#Look-up-Tables-FPGA-Programming-And-Design-Methodology)
    * [Introduction To Basys FPGA Boards And Vivado](#Introduction-To-Basys-FPGA-Boards-And-Vivado)
  * [Vivado Counter](#Vivado-Counter)
    * [Vivado-Verilog explanation](#Vivado-Verilog-explanation)
    * [Vivado Simulation Elaboration](#Vivado-Simulation-Elaboration)
    * [Vivado map pins](#Vivado-map-pins)
    * [Theory Slack](#Theory-Slack)
  * [VIO Counter](#VIO-Counter)
    * [Introduction Theory](#Introduction-Theory) 
    * [VIO Code](#VIO-Code)
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
    
 # Day 1: 
 ***
 
 ## FPGA Introduction
 
 ### What Is FPGA And FPGA Architecture?
 
 * **History of Programmable logic**
   * PLA - Programmable logic devices
   * CPLD - Complex Programmable logic devices
   * FPGA - Field Programmable Gate Array
   * Generate customizable hardware
   * Study of effects of area, speed, power of the digital circuits
 
 **FPGA Board used in this workshop is Basys3**
 
  <p align="center" width="100%">
  <img src="https://user-images.githubusercontent.com/68154219/171170305-a5c4ec0a-c3a6-4708-ad97-69ccdb79bcd5.png"> 
  </p>

* **What is an FPGA**
  * A "field programmable" gate array: Integrated circuit designed to be configured by a designer. 
  * FPGA configuration is specified using HDL similar to an ASIC (Application Specific Integrated Circuit)
  * Logic design in FPGA is different. It uses LUT, Flip-flops, configurable logic blocks.

* **Difference between ASIC and FPGA**

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171171692-3eba236d-3791-4963-b797-c6f7e3c12cb8.png"> 
</p>

* **Applications**
  * Hardware acceleration
  * Signal Processing
  * Device controllers
  * Embedded systems
  * Aerospace
  * High Performance Computing
  * Machine Learning
 
 * **FPGA Architechture**
 
<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171174410-742f1df8-12e1-4450-bd61-a5cea1a821aa.png"> 
</p>

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171175376-d327132b-f9c0-4380-8641-c9795872bf3b.png"> 
</p>

* Configurable Logic Blocks (CLB) implement combinatorial and sequential logic. Based on LUT and Flipflop/latches.
  * Look-Up Tables (LUT)which implement logic functions - truth table
  * Carry and Control Logic - Implements arithmetic operations
  * FlipFlops(FF)/Latches
* Memory Elements
* Programmable I/O blocks - Configurable I/Os for external interface connections
* Programmable Interconnect - Wires to connect inputs, CLBs

### Look-up Tables, FPGA Programming And Design Methodology

Lookup Table with N inputs can be used to implement any combinational function of N inputs

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171406122-1f94d32e-2c8c-4715-9a82-8e87d12722db.png"> 
</p>

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171407648-4c48ab0a-3c39-407f-8385-4e9bac49d7d5.png"> 
</p>

### Introduction To Basys FPGA Boards And Vivado

**What are not synthesizable codes**

* Delays #100 - Write counters, and generate a signal after a certain count to create a delay
* Initial block (used only in testbench)
* UDP (User defined primitive) - nmos, pmos
* Runtime/Dynamic Memory Allocation: Indeterminate sizes cannot be synthesised -> Convert into fixed size memory
* Infinite loops -> Convert into a finite loop

**Different ways of programming**
* Local programming on the Basys3 Board
* Remote Programming
  * Inputs through Virtual Inputs/Outputs and Output observed on the board
  * Inputs through Virtual Inputs/Outputs and Output observed on Integrated Logic Analyser (ILA)

## Vivado Counter

### Vivado-Verilog explanation

### Vivado Simulation Elaboration

**Behavioural Simulation result for 4bit Counter** 

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171993060-d8f62a19-7b9d-472c-bce8-3130e0ad89d3.png"> 
</p>

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171993200-0e573333-0cf1-437d-b450-afc0a06052e3.png"> 
</p>

### Vivado map pins

* Open Elaborated Design -> I/O Planning (Upper Right corner drop down)

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171999574-9d66514a-f4cf-4868-8932-33df1d632560.png"> 
</p>

* Schematic

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171999766-9f240e04-4ae4-4f36-a10a-21ce51b90818.png"> 
</p>

* To generate constraint file
Change I/O Std and Package pin as shown. Assign Leds to the counter_out. Observe the datasheet of board to assign the pins. Save the file as constraint.

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171999828-9f55011d-79d7-4753-925e-60ec68aac7c2.png"> 
</p>

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/171999927-e2b907a4-b89a-4604-9297-01687e5654b1.png"> 
</p>

### Theory Slack

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172000088-1940ed57-3da8-4a11-a34f-2051369c8d6d.png"> 
</p>

Tcq + Tlogic < (T - Tsetup)

###  Vivado Synthesis

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172000444-81e72305-91d1-46dc-b381-8e20006211b6.png"> 
</p>

* Go to Constraint Wizard -> select clk and enter frequency. Run the synthesis again and open the Timing Report

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172001331-c2a63d63-4a06-4169-a2c4-77bfb0d900dc.png"> 
</p>

* Schematics 

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172021718-61019962-f667-4bf9-8958-48ab5b8ea6c5.png"> 
</p>

* Timimg Summary

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172021791-a669f2a7-5e14-45cb-b2b4-5ea61d317aae.png"> 
</p>

* Power Summary

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172023114-803143c3-96ae-4dc3-a37a-02443a8e91c9.png"> 
</p>

## VIO Counter

### Introduction Theory

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172023847-57e09e38-128c-4ffd-be54-7cca8136fa2e.png"> 
</p>

### VIO Code

**Steps**
* Modify the counter code accordingly to make all inputs into wires and output to reg except the clock
* Create a VIO template using IP Catalog
  * Add probes - input and output
  * Change the probe width accordingly
* Click on IP sources -> instantiation templates -> veo for verilog , vho for vhdl
* Copy paste the template into your code
  * Change the module probes names of VIO template just copied
  * Input and output should be assigned according to the comments mentioned here
*  Design is ready to simulate

* **VIO instance**

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172024786-96f9c1d2-1e01-4277-b4a5-3355d363cafe.png"> 
</p>

* **Copy paste vio instance and make changes in input output in the code**

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/68154219/172024899-6096ddb4-5ec1-400c-bfdb-ac68bd134a72.png"> 
</p>









