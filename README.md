<img width="1520" height="811" alt="image" src="https://github.com/user-attachments/assets/57228a03-77af-45a4-aa4d-5b53bcddfdae" /># 8 bit cpu

## Table of Contents

- [How to View](#How_to_View)
- [Brief Overview](#Overview)
- [Instruction Register](#Instruction_Register)
- [registers](#Registers)
- [ALU](#ALU)
- [Mover](#Mover)
- [RAM_and_Memory Address manager](#RAM_and_Memory_Address_Manager)
- [Program Counter](#program_counter)
- [Assembly](#assembly)
- [Input](#Input)
- [Output](#Output)

## How_to_View

To view my project download the file titled "cpu_attempt_1.circ" and download logisim-evolution. Then open the file using logisim-evolution.

## Overview

This cpu consists of 4 main registers which hold 8 bits each. It consists of 16 bytes of ram controlled by the memory address manager. The alu allows the cpu to perform addition, subtraction, checking if two numbers are equal, checking if one number is greater than another number. The input consists is limited to 16 lines of code and the output consists of an 8x8 display which displays the result in binary.

## Instruction_Register

The instruction register is a decoder that converts the values of the instructions given in binary into a on/off value of the instruction. It's outputs are connected other components of the cpu like the ALU, Mover, Program Counter, Memory Address Manager and the Output Control.

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image2.png?raw=true" width="300" />    <img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image1.png?raw=true" width="500" />

## Registers

There are 4 main registers which I will be refering to as r0, r1, r2 r3. To perform any operations on numbers. They first have to be moved into a register. There is also a execution register which contains the command being currently executed. 
The last bit in the registers is used as a buffer to avoid issues related to delays during subtraction.

Main Registers: 

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image3.png?raw=true" width="300" />

Execution Register:

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image4.png?raw=true" width="600" />

## ALU

The Arithmetic and Logical unit in my cpu can perform the following things

- Addition

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image8.png?raw=true" width="350" />
  
- Subtraction
  
<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image7.png?raw=true" width="350" />

- And
- Or
- Xor
- Equal to
- Greater Than
  
<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image6.png?raw=true" width="350" />

## Mover

The mover performs the task of moving data into the registers.

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image9.png?raw=true" width="350" />

## RAM_and_Memory_Address_Manager

The cpu is connected to a memory address manager which is connected to 16 bytes of RAM. The RAM can be written to by the data stored in the main registers, and the data stored in the ram can be moved into the main registers. This can be done using the get and set functions.

RAM:

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image10.png?raw=true" width="350" />

Memory Address Manager: 

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image11.png?raw=true" width="350" />
