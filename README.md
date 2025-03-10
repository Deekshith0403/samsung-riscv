# Samsung-RISCV
This course teaches users about VLSI chip design and RISC-V using open-source tools and is based on the RISC-V architecture. Kunal Ghosh Sir is the workshop's instructor.
## Profile Details:
##### Name: Deekshith K M
##### College: Vidyavardhaka College of Engineering
##### Email: deekshithkm2003@gmail.com
##### GitHub Profile: Deekshith0403
##### LinkedIN: www.linkedin.com/in/deekshith-k-m 
<details>
<summary><b>Task 1:</b>Task 1: Review lab videos on C programming and RISC-V architecture. Perform the task of compiling C code using both the GCC compiler and the RISC-V compiler, demonstrating an understanding of the compilation process for each.simulator</summary>   
<br>

##### Task 1: Review lab videos on C programming and RISC-V architecture. Perform the task of compiling C code using both the GCC compiler and the RISC-V compiler, demonstrating an understanding of the compilation process for each.

## C and RISC-V Programming Labs
This repository provides a detailed guide to compiling C programs and generating assembly code using both the standard GCC compiler and the RISC-V GCC compiler. It covers all essential steps and explanations for understanding the compilation and debugging workflows.

### Lab 1: Working with C Language
#### Compiling a .c File Locally
   1. Launch the bash terminal and navigate to the directory where you want to create your source file.
   2. Use the following command to create and open a new .c file for editing:
      
   ``` sh
   gedit sum_1ton.c
   ```

   ![s2](https://github.com/user-attachments/assets/d4988890-b199-42e9-b019-89f7064a3a99)
   
   3. Save your changes and compile the program with the following commands:
      
   ``` sh
   gcc sum_1ton.c
   ./a.out
   ```

   ![s4](https://github.com/user-attachments/assets/4c9efc95-21fc-4adc-9f4d-19d888500e7f)
   
   Compilation and execution are now complete.
   
   ### Lab 2: Programming with RISC-V
   #### Compiling a Program Using the RISC-V GCC Compiler
   1. Confirm that the RISC-V GCC compiler is installed and properly set up on your system.
   2. Check the contents of the .c file using the cat command:
      
      ``` sh
      cat sum_1ton.c
      ```
      
      ![s6](https://github.com/user-attachments/assets/e37bf503-24ff-4fa8-b954-18cb81f32682)
      
   4. Compile the program for RISC-V architecture with the following command:
      
      ``` sh
      riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum_1ton.o sum_1ton.c
      ```
   6. To view the assembly code, disassemble the compiled object file:
      
      ``` sh
      riscv64-unknown-elf-objdump -d sum_1ton.o
      ```
      
      ![s12](https://github.com/user-attachments/assets/74485935-6d5d-44a9-9f0a-18141b5da482)
      
   8. Use the /main search command in the terminal to find the main function in the disassembled output.

      ![s17](https://github.com/user-attachments/assets/20fad9fb-5d2a-4f6a-ba4f-b746b8e29a09)

  ### Explanation of Commands and Options:
  1. -mabi=lp64: Sets the Application Binary Interface (ABI) for 64-bit data types, suitable for RISC-V 64-bit architecture.
  2. -march=rv64i: Specifies the RISC-V 64-bit integer instruction set architecture.
  3. -O1: Activates basic optimization to improve performance without significantly increasing compilation time.
  4. riscv64-unknown-elf-objdump: This utility disassembles RISC-V binaries, allowing you to analyze and debug the code structure efficiently.
</details>

<details>   
<summary><b>Task 2:</b> Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler simulator</summary>   
<br>

##### Task 2:Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler simulator
## RISC-V ISA Simulation with SPIKE
This repository offers guidance on setting up and using SPIKE, a RISC-V ISA simulator, along with the Proxy Kernel (pk) for executing programs. It includes detailed instructions to install the required tools, perform simulations, and debug RISC-V programs efficiently. Follow the steps provided to get started with RISC-V development using SPIKE.

## About SPIKE
SPIKE is a C++-based open-source simulator for the RISC-V ISA. It provides an efficient environment for testing and debugging RISC-V programs, offering support for both standalone applications and complete operating systems like Linux, without requiring physical hardware.

## Simulating RISC-V with SPIKE
To verify the setup, compile and run a sample program (`sum_1ton.c`) using both the GCC compiler and the RISC-V toolchain.
### Using GCC Compiler:
~~~ sh
gcc add.c
./a.out
~~~
![VirtualBox_vdsworkshop_14_01_2025_00_04_48](https://github.com/user-attachments/assets/a781d490-d3a0-47a8-a8c7-153ecc32d427)

### Using RISC-V Compiler:
``` sh
spike pk add.o
```
## Analyzing the Assembly Code
### Objdump Analysis:
Generate the corresponding assembly code using the following command:
``` sh
riscv64-unknown-elf-objdump -d sum_1ton.o | less
```
![VirtualBox_vdsworkshop_13_01_2025_19_54_18](https://github.com/user-attachments/assets/9434e51b-379a-431e-ac19-4fb4e9031e41)

### Debugging with SPIKE:
1. Open the debugger using the command:
``` sh
spike -d pk product.o
```
2. Perform debugging operations in the terminal.
## Optimization Levels
Snapshots of the RISC-V object dump at various optimization levels (-O1 and -Ofast) offer valuable insights into the impact of compiler optimizations on the generated assembly code. Use these options during compilation to examine the differences.

-O1 Optimization

-Ofast Optimization
![image](https://github.com/user-attachments/assets/f840b18c-79b8-4e2c-a0d2-1de07ff47a8a)

</details>
<details>
<summary><b>Task 3:</b> The task is to determine the instruction type for each of the provided instructions and provide their corresponding 32-bit instruction codes in the appropriate format.format</summary>

# Understanding RISC-V and Its Instruction Formats
## Understanding RISC-V and Its Instruction Formats

### About RISC-V
RISC-V is an open-source Instruction Set Architecture (ISA) designed to empower developers in creating processors optimized for specific applications. Rooted in the Reduced Instruction Set Computer (RISC) principles, RISC-V marks the fifth iteration of processors developed under this concept. Its open and license-free model allows developers to use RISC-V without incurring licensing fees, offering an attractive alternative to proprietary processor technologies.

### RISC-v Instruction Formats
The instruction format of a processor specifies the structure of machine language instructions for execution. These instructions consist of binary code (0s and 1s), with each segment indicating details about data locations and the operations to execute. In RISC-V, there are six main instruction formats:
1. **R-format**
2. **I-format**
3. **S-format**
4. **B-format**
5. **U-format**
6. **J-format**

   ![instruction_formats](https://github.com/user-attachments/assets/a661f728-f5d5-493d-a4d9-d4a79b53618a)

Let’s examine each format in detail.

---

#### 1. R-type Instruction
R-type (Register-type) instructions perform operations directly on registers instead of memory locations. These instructions are primarily used for arithmetic and logical computations. Each R-type instruction is 32 bits long and is divided into six distinct fields:

##### Structure:

| Field Name | Size  | Description                            |
|------------|-------|----------------------------------------|
| Opcode     | 7 bits| Determines the instruction type        |
| rd         | 5 bits| Destination register                  |
| func3      | 3 bits| Specifies the type of operation       |
| rs1        | 5 bits| First source register                 |
| rs2        | 5 bits| Second source register                |
| func7      | 7 bits| Additional operation specification    |

##### Example: SUB Instruction (R-type)

**Instruction:** `SUB r12, r8, r3`  
- **Operation:** Subtracts the value in register `r3` from the value in `r8`, storing the result in `r12`.  

**Field Breakdown:**  
- **Opcode:** `0110011`  
- **rd (Destination):** `r12` -> `01100`  
- **rs1 (Source 1):** `r8` -> `01000`  
- **rs2 (Source 2):** `r3` -> `00011`  
- **func3:** `000`  
- **func7:** `0100000`  

**32-bit Instruction:**  
`0100000_00011_01000_000_01100_0110011`
##### Example: AND Instruction (R-type)

**Instruction:** `AND r11, r2, r5`  
- **Operation:** Performs a bitwise AND operation between the values in registers `r2` and `r5`, storing the result in `r11`.  

**Field Breakdown:**  
- **Opcode:** `0110011`  
- **rd (Destination):** `r11` -> `01011`  
- **rs1 (Source 1):** `r2` -> `00010`  
- **rs2 (Source 2):** `r5` -> `00101`  
- **func3:** `111`  
- **func7:** `0000000`  

**32-bit Instruction:**  
`0000000_00101_00010_111_01011_0110011`

##### Example: OR Instruction (R-type)

**Instruction:** `OR r13, r6, r7`  
- **Operation:** Performs a bitwise OR operation between the values in registers `r6` and `r7`, storing the result in `r13`.  

**Field Breakdown:**  
- **Opcode:** `0110011`  
- **rd (Destination):** `r13` -> `01101`  
- **rs1 (Source 1):** `r6` -> `00110`  
- **rs2 (Source 2):** `r7` -> `00111`  
- **func3:** `110`  
- **func7:** `0000000`  

**32-bit Instruction:**  
`0000000_00111_00110_110_01101_0110011`

  ![R-type_instruction_format](https://github.com/user-attachments/assets/83cd50ac-ab4e-47f5-abb7-5d7acf583b35)

---

#### 2. I-type Instruction
I-type (Immediate-type) instructions operate using a combination of a register and an immediate (constant) value. They are commonly utilized for load operations and computations involving immediate values.

##### Structure:

| Field Name | Size  | Description                            |
|------------|-------|----------------------------------------|
| Opcode     | 7 bits| Determines the instruction type        |
| rd         | 5 bits| Destination register                  |
| func3      | 3 bits| Specifies the type of operation       |
| rs1        | 5 bits| Source register                       |
| imm[11:0]  | 12 bits| Immediate value                      |

##### Example: ORI Instruction (I-type)

**Instruction:** `ORI r10, r3, 15`  
- **Operation:** Performs a bitwise OR operation between the value in `r3` and the immediate value `15`, storing the result in `r10`.  

**Field Breakdown:**  
- **Opcode:** `0010011`  
- **rd (Destination):** `r10` -> `01010`  
- **rs1 (Source):** `r3` -> `00011`  
- **imm[11:0] (Immediate):** `000000001111`  
- **func3:** `110`  

**32-bit Instruction:**  
`000000001111_00011_110_01010_0010011`

  ![I-type_instruction_format](https://github.com/user-attachments/assets/4093ac10-bf93-4fdf-be25-8f062c2fdf5c)

---

#### 3. S-type Instruction

S-type (Store-type) instructions store register values into memory locations.

##### Structure:

| Field Name | Size  | Description                            |
|------------|-------|----------------------------------------|
| Opcode     | 7 bits| Determines the instruction type        |
| rs1        | 5 bits| Base address register                 |
| rs2        | 5 bits| Source register                       |
| imm[11:5]  | 7 bits| Upper immediate value                  |
| imm[4:0]   | 5 bits| Lower immediate value                  |
| func3      | 3 bits| Specifies the type of operation       |

##### Example: SB Instruction (S-type)

**Instruction:** `SB r5, 4(r2)`  
- **Operation:** Stores the least significant byte of the value in `r5` into the memory at the address `r2 + 4`.  

**Field Breakdown:**  
- **Opcode:** `0100011`  
- **rs1 (Base Address):** `r2` -> `00010`  
- **rs2 (Source):** `r5` -> `00101`  
- **imm[11:5] (Upper Immediate):** `0000000`  
- **imm[4:0] (Lower Immediate):** `00100`  
- **func3:** `000`  

**32-bit Instruction:**  
`0000000_00101_00010_000_00100_0100011`

  ![image](https://github.com/user-attachments/assets/01eee62a-1120-4884-a251-2a9bb4df79f5)

---

#### 4. B-type Instruction

B-type (Branch-type) instructions are used for branching operations that depend on specific conditions.

##### Structure:

| Field Name | Size  | Description                            |
|------------|-------|----------------------------------------|
| Opcode     | 7 bits| Determines the instruction type        |
| rs1        | 5 bits| Source register 1                      |
| rs2        | 5 bits| Source register 2                      |
| imm[12|10:5|4:1|11] | 13 bits| Branch offset                |
| func3      | 3 bits| Specifies the condition for branching |

##### Example: BEQ Instruction (B-type)

**Instruction:** `BEQ r2, r3, 16`  
- **Operation:** Branches to the address `PC + 16` if the value in `r2` is equal to the value in `r3`.  

**Field Breakdown:**  
- **Opcode:** `1100011`  
- **rs1:** `r2` -> `00010`  
- **rs2:** `r3` -> `00011`  
- **imm[12|10:5|4:1|11]:** `0000010000`  
- **func3:** `000`  

**32-bit Instruction:**  
`0000000_00011_00010_000_10000_1100011`

##### Example: BNE Instruction (B-type)

**Instruction:** `BNE r1, r2, 10`  
- **Operation:** Branches to the address `PC + 10` if the value in `r1` is not equal to the value in `r2`.  

**Field Breakdown:**  
- **Opcode:** `1100011`  
- **rs1:** `r1` -> `00001`  
- **rs2:** `r2` -> `00010`  
- **imm[12|10:5|4:1|11]:** `0000010100`  
- **func3:** `001`  

**32-bit Instruction:**  
`0000000_00010_00001_001_01000_1100011`
  
  ![B_type_instruction_format](https://github.com/user-attachments/assets/f546b492-4b2c-4857-bc4b-a4d45846ca0e)

---

#### 5. U-type Instruction

U-type (Upper Immediate) instructions are used to load immediate values into the destination register, typically placing the immediate value in the upper 20 bits of the register.

##### Structure:

| Field Name | Size  | Description                            |
|------------|-------|----------------------------------------|
| Opcode     | 7 bits| Determines the instruction type        |
| rd         | 5 bits| Destination register                   |
| imm[31:12] | 20 bits| Upper immediate value                 |

  ![U-type_instruction_format](https://github.com/user-attachments/assets/c0e9c34f-c3ad-4bcc-9538-df11e68ef4ab)

---

#### 6. J-type Instruction

J-type (Jump-type) instructions are used to perform jump operations, typically employed for control flow changes such as loops and function calls.

##### Structure:

| Field Name | Size  | Description                            |
|------------|-------|----------------------------------------|
| Opcode     | 7 bits| Determines the instruction type        |
| rd         | 5 bits| Destination register                   |
| imm[20|10:1|11|19:12] | 20 bits| Jump offset                |

  ![J-type_instruction_format](https://github.com/user-attachments/assets/b367fe02-c1f8-45d0-9f54-020794f17117)

---
# RISC-V 15 Unique Instructions and Their 32-Bit Machine Codes

This repository documents 15 unique RISC-V instructions extracted from an object file, along with their corresponding 32-bit machine codes and instruction formats. This serves as a reference for understanding the RISC-V assembly language and its instruction encodings.

![obj](https://github.com/user-attachments/assets/26ce0a34-2824-4e89-baa8-06f51078857d)

---

## List of Instructions and Machine Codes

1. **`lui a0, 0x21` (Load Upper Immediate)**  
   - **Format**: U-type  
   - **Opcode**: `0110111`  
   - **Machine Code**: `0x00021537`  
   - **Binary**: `00000000001000010101000000110111`

2. **`li a3, 50` (Load Immediate)**  
   - **Format**: I-type  
   - **Opcode**: `0010011`  
   - **Machine Code**: `0x03200693`  
   - **Binary**: `00000011001000000000011010010011`

3. **`li a2, 5` (Load Immediate)**  
   - **Format**: I-type  
   - **Opcode**: `0010011`  
   - **Machine Code**: `0x00500613`  
   - **Binary**: `00000000010100000000001100010011`

4. **`li a1, 10` (Load Immediate)**  
   - **Format**: I-type  
   - **Opcode**: `0010011`  
   - **Machine Code**: `0x00a00593`  
   - **Binary**: `00000000101000000000001100110011`

5. **`addi a0, a0, 352` (Add Immediate)**  
   - **Format**: I-type  
   - **Opcode**: `0010011`  
   - **Machine Code**: `0x16050513`  
   - **Binary**: `00010110000001010000000001010011`

6. **`j 103f4` (Jump)**  
   - **Format**: J-type  
   - **Opcode**: `1101111`  
   - **Machine Code**: `0x3300006f`  
   - **Binary**: `00110011000000000000000001101111`

7. **`auipc a5, 0xffff0` (Add Upper Immediate to PC)**  
   - **Format**: U-type  
   - **Opcode**: `0010111`  
   - **Machine Code**: `0xffff0797`  
   - **Binary**: `11111111111111110000011110010111`

8. **`addi a5, a5, -200` (Add Immediate)**  
   - **Format**: I-type  
   - **Opcode**: `0010011`  
   - **Machine Code**: `0xf3878793`  
   - **Binary**: `11110011000001111000111110010011`

9. **`beqz a5, 100e0` (Branch if Equal to Zero)**  
   - **Format**: B-type  
   - **Opcode**: `1100011`  
   - **Machine Code**: `0x00078863`  
   - **Binary**: `00000000000001111000100001100011`

10. **`ret` (Return)**  
    - **Format**: I-type  
    - **Opcode**: `1100111`  
    - **Machine Code**: `0x00008067`  
    - **Binary**: `00000000000010000000011001110111`

11. **`auipc gp, 0x13` (Add Upper Immediate to PC)**  
    - **Format**: U-type  
    - **Opcode**: `0010111`  
    - **Machine Code**: `0x00013197`  
    - **Binary**: `00000000000000010011000110010111`

12. **`addi gp, gp, -1756` (Add Immediate)**  
    - **Format**: I-type  
    - **Opcode**: `0010011`  
    - **Machine Code**: `0x92418193`  
    - **Binary**: `10010010000000011000000110010011`

13. **`sub a2, a2, a0` (Subtract)**  
    - **Format**: R-type  
    - **Opcode**: `0110011`  
    - **Machine Code**: `0x40a60633`  
    - **Binary**: `01000010100110000000001100011011`

14. **`jal ra, 102d4` (Jump and Link)**  
    - **Format**: J-type  
    - **Opcode**: `1101111`  
    - **Machine Code**: `0x1d4000ef`  
    - **Binary**: `00011101010000000000000011101111`

15. **`lw a0, 0(sp)` (Load Word)**  
    - **Format**: I-type  
    - **Opcode**: `0000011`  
    - **Machine Code**: `0x00012503`  
    - **Binary**: `00000000000000010010010010100011`

---

</details>

<details>
<summary><b>Task 4:</b> Functional Simulation of RISC-V Core</summary>   
<br>

## 2. BLOCK DIAGRAM OF RISC-V RV32I
![image](https://user-images.githubusercontent.com/110079631/181293948-beb8622c-7696-4b06-b6c9-eeab9b8ab9d3.png)

## 3. INSTRUCTION SET OF RISC-V RV32I
![image](https://user-images.githubusercontent.com/110079631/181298133-60269bc2-01da-4b5c-8b42-69057b8dc15c.png)

# RISC-V Core Functional Simulation 
## 4. FUNCTIONAL SIMULATION

### 4.1 About iverilog and gtkwave
- Icarus Verilog is an implementation of the Verilog hardware description language.
- GTKWave is a fully featured GTK+ v1. 2 based wave viewer for Unix and Win32 which reads Ver Structural Verilog Compiler generated AET files as well as standard Verilog VCD/EVCD files and allows their viewing.

### 4.2 Installing iverilog and gtkwave

- **For Ubuntu**

 Open your terminal and type the following to install iverilog and GTKWave
 ```
 $   sudo apt get update
 $   sudo apt get install iverilog gtkwave
 ```

- **To clone the repository and download the netlist files for simulation , enter the following commands in your terminal.**

 ```
 $ git clone https://github.com/vinayrayapati/iiitb_rv32i
 $ cd iiitb_rv32i
 ```
- **To simulate and run the verilog code , enter the following commands in your terminal.**

```
$ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
$ ./iiitb_rv32i
```
- **To see the output waveform in gtkwave, enter the following commands in your terminal.**

`$ gtkwave iiitb_rv32i.vcd`

Installed iverilog and GTKwave 

![VirtualBox_vdsworkshop_23_01_2025_16_56_05](https://github.com/user-attachments/assets/9727fdde-e6b7-42ff-b868-6c2182a4ce8f)

---

A directory named chethan was created 
```bash
mkdir chethan
```
The following commands were executed

![VirtualBox_vdsworkshop_23_01_2025_16_17_14](https://github.com/user-attachments/assets/bcec5209-824e-4cb2-94b1-ffa63434993c)

---

The below waveform was generated

![VirtualBox_vdsworkshop_23_01_2025_16_26_23](https://github.com/user-attachments/assets/52081c24-a338-4b58-a910-434054968ef2)

---

### Now analysing the output waveform of various instructions

Instruction 1: ADD R6, R2, R1 

![VirtualBox_vdsworkshop_03_02_2025_19_32_43](https://github.com/user-attachments/assets/4dabab4c-ee6a-42d0-ba4f-5af076e7c9ee)

---

Instruction 2: SUB R7, R1, R2

![VirtualBox_vdsworkshop_03_02_2025_19_34_13](https://github.com/user-attachments/assets/f6df1f47-829b-41e7-baf9-7039a116425e)

---

Instruction 3: AND R8, R1, R3

![VirtualBox_vdsworkshop_03_02_2025_19_35_54](https://github.com/user-attachments/assets/71340e1f-7abc-49a8-8877-7bcb861f5b29)

---

Instruction 4: OR R9, R2, R5

![VirtualBox_vdsworkshop_03_02_2025_19_36_55](https://github.com/user-attachments/assets/c4cd1c52-4895-4fce-9c40-f32f600794b7)

---

Instruction 5: XOR R10, R1, R4

![VirtualBox_vdsworkshop_03_02_2025_19_39_38](https://github.com/user-attachments/assets/d1202e87-d9b7-4890-b943-8a479b18cdcc)

---

Instruction 6: SLT R1, R2, R4

![VirtualBox_vdsworkshop_03_02_2025_19_40_14](https://github.com/user-attachments/assets/249d7109-25df-46ff-bd65-cbe9d837e915)

---

Instruction 7: ADDI R12, R4, 5

![VirtualBox_vdsworkshop_03_02_2025_19_43_32](https://github.com/user-attachments/assets/27f5f1e1-6d4f-4d20-9c49-2f7d624f5cf5)

---

Instruction 8: BEQ R0, R0, 15

![VirtualBox_vdsworkshop_03_02_2025_19_49_59](https://github.com/user-attachments/assets/a4ac6de4-3744-42da-a8f4-89814867c7f1)

---

Instruction 9:sw r3,r1,2

![VirtualBox_vdsworkshop_03_02_2025_20_17_08](https://github.com/user-attachments/assets/38bb8f76-c631-4485-86c9-d512f7d70039)

---

Instruction 10:lw r13,r1,2

![VirtualBox_vdsworkshop_03_02_2025_19_54_24](https://github.com/user-attachments/assets/829be81f-d76c-4d03-b815-683f23a9f78d)

---

Full 5-stage instruction pipeline and pc-increment description Waveform is given below:

![VirtualBox_vdsworkshop_03_02_2025_19_57_19](https://github.com/user-attachments/assets/abc1afa2-2cfe-4d47-b8c8-37ef74456910)


</details>

<details>
<summary><b>Task 5:</b> Intruder Detection System Using ultrasonic Sensor & VSDSquadron Mini</summary>   
<br>
   
# Intruder Detection System Using ultrasonic Sensor & VSDSquadron Mini  

![circuit_diagram](https://github.com/user-attachments/assets/8109545e-439b-4899-a70d-f81834b828c3)
 

## Overview  

The **Intruder Detection System** is a real-time security solution that detects **unauthorized movement using an Ultrasonic Sensor** and processes signals via the **VSDSquadron Mini board**. Upon detecting an intruder, the system **activates an alert mechanism**, signaled by an LED.  

Designed for **efficiency, scalability, and cost-effectiveness**, this system can be further **enhanced with wireless communication, AI-based recognition, and cloud integration**, making it a versatile solution for modern security needs.

## Key Features

- ✅ Instant intrusion detection using an ultrasonic sensor for real-time security
- ✅ High-speed FPGA-based processing ensures rapid threat response
- ✅ Flexible alert options – Supports buzzer, LED, or wireless notifications
- ✅ Expandable architecture – Easily integrates AI, cloud, and IoT for advanced monitoring
- ✅ Cost-effective & power-efficient for long-term, reliable operation
- ✅ User-friendly setup with minimal maintenance requirements
---

## Components Required  

| **Component**      | **Specification** |
|--------------------|------------------|
| VSD Squadron Mini | FPGA Development Board |
| ultrasonic Sensor         |Motion & Distance Indicator |
| LED              | Visual Alert |
| 220-ohm Resistor | Current Limiting |
| Jumper Wires     | Circuit Connections |
| Breadboard       | Prototyping |

---

## Circuit Pin Connections  

| **Component** | **Pin on Board** |
|--------------|------------------|
| **LED**      | PD3 |
| **Ultrasonic Sensor** |
| **VCC**| 3.3V |
| **ground**| gnd |
| **trig pin** | PD4 |
| **Echo pin** | PD2 |

---

## How It Works

The system functions by emitting a brief ultrasonic pulse via **PD2** and detecting its echo through **PD4**. **When an object is within range, the pulse is reflected back to the sensor, generating a high signal on the ECHO pin**. Upon detection, the processor activates an LED, notifying the user of the object's presence.

---

## Applications  
This system is highly adaptable, making it suitable for a wide range of applications:

### 🔹 Home Security
- -> Detects intruders in residences, apartments, and gated communities
- -> Integrates with smart home systems for real-time alerts
### 🔹 Industrial & Commercial Security
- -> Safeguards factories, warehouses, and office premises
- -> Controls access to restricted and high-security areas
### 🔹 Military & Border Surveillance
- -> Monitors unauthorized movements in restricted zones
- -> Supports border security and military intelligence operations
### 🔹 ATM & Bank Protection
- -> Identifies suspicious activity near ATMs and vaults
- -> Triggers instant alarms to prevent unauthorized access
### 🔹 Smart Parking & Access Management
- -> Regulates vehicle entry and exit in parking facilities
- -> Automates barriers, gates, and restricted access points
### 🔹 Wildlife Conservation & Agricultural Security
- -> Tracks animal movement in protected zones and farmlands
- -> Assists in anti-poaching efforts and livestock protection
### 🔹 Healthcare & Elderly Assistance
- -> Detects falls, abnormal movements, or patient distress
- -> Enhances security and monitoring in hospitals and elder care facilities

---

#### Future Enhancements  

🔹 **AI-driven detection** for improved precision and object classification  
🔹 **Wireless communication** for seamless remote alerts and real-time monitoring  
🔹 **Cloud integration** for centralized data analysis and security management  
🔹 **Multi-sensor collaboration** to expand coverage and enhance threat detection

---

</details>

<details>
<summary><b>Task 6:</b> Intruder Detection using Ultrasonic Sensor</summary>   
<br>
   
# Intruder Detection using IR Sensor

## Overview
This project is part of Task 6 of the Samsung RISC-V program. The objective is to design an intruder detection system using an Ultrasonic sensor, and  an LED. When an intruder is detected, the system activates an alarm (buzzer) and visual alert (LED) to notify about unauthorized access.

![circuit_diagram](https://github.com/user-attachments/assets/a75585a8-893d-4575-9f1f-d7eeffc70391)

## Components Required:

1. VSD Squadron Mini
2. Ultrasonic Sensor
3. LED
4. 220 ohm Resistor
5. Jumper wires
6. Breadboard

## Pin Connections:

| **Component** | **Pin on Board** |
|--------------|------------------|
| **LED**      | PD3 |
| **Ultrasonic Sensor** |
| **VCC**| 3.3V |
| **ground**| gnd |
| **trig pin** | PD4 |
| **Echo pin** | PD2 |

## Working Principle:
The system functions by emitting a brief ultrasonic pulse via **PD2** and detecting its echo through **PD4**. **When an object is within range, the pulse is reflected back to the sensor, generating a high signal on the ECHO pin**. Upon detection, the processor activates an LED, notifying the user of the object's presence.

## Code Implementation:
---
The program will be written in C and deployed on the VSD Squadron Mini board. It will read the sensor input and control the LED and buzzer accordingly.

### API Reference:
- USART_Printf_Init() : Initializes the USART peripheral for debugging and output.
- Delay_Ms() : Generates a millisecond delay, useful for timing and sensor control.
- GPIO_ReadInputDataBit() : Reads the state of an input pin.
- GPIO_WriteBit() : Sets or clears a specific output pin, used for controlling the LED and the ultrasonic sensor’s trigger.
  
```bash
#include <ch32v00x.h>
#include <debug.h>

void GPIO_Config(void) {
    GPIO_InitTypeDef GPIO_InitStructure = {0};

    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE);

    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_0 | GPIO_Pin_4;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU;
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_2 | GPIO_Pin_3;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOD, &GPIO_InitStructure);
}

int main(void) {
    uint8_t echo_status = 0;

    SystemCoreClockUpdate();
    Delay_Init();
    GPIO_Config();

    while (1) {
        GPIO_WriteBit(GPIOD, GPIO_Pin_2, SET);
        Delay_Ms(10);
        GPIO_WriteBit(GPIOD, GPIO_Pin_2, RESET);

        echo_status = GPIO_ReadInputDataBit(GPIOD, GPIO_Pin_4);

        if (echo_status == 1) {
            GPIO_WriteBit(GPIOD, GPIO_Pin_3, RESET);
            Delay_Ms(2500);
        } else {
            GPIO_WriteBit(GPIOD, GPIO_Pin_3, SET);
        }
    }
}

```
---
![Intruder_detectior_2](https://github.com/user-attachments/assets/b738bb7d-3bc7-4bff-81a3-190444cecfdf)


![Intruder_detectior_1](https://github.com/user-attachments/assets/b11e4882-100c-44e9-86b0-4ee2ee704114)
  </details>
