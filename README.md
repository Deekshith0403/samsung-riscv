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

</details>
