# 8 bit cpu

## Table of Contents

- [How to View](#How_to_View)
- [Brief Overview](#Overview)
- [Instruction Register](#Instruction_Register)
- [registers](#Registers)
- [ALU](#ALU)
- [Mover](#Mover)
- [RAM](#RAM)
- [Memory Address manager](#memory_address_manager)
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
- Subtraction
  
<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image7.png?raw=true" width="350" />

- And
- Or
- Xor
- Equal to
- Greater Than
  
<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image6.png?raw=true" width="350" />
