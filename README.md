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







