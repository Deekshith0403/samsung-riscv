# Samsung-RISCV
This course teaches users about VLSI chip design and RISC-V using open-source tools and is based on the RISC-V architecture. Kunal Ghosh Sir is the workshop's instructor.
## Profile Details:
##### Name: Deekshith K M
##### College: Vidyavardhaka College of Engineering
##### Email: deekshithkm2003@gmail.com
##### GitHub Profile: Deekshith0403
##### LinkedIN: www.linkedin.com/in/deekshith-k-m 
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




