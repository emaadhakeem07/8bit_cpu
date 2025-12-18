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

## How to View

To view my project download the file titled "cpu_attempt_1.circ" and download logisim-evolution. Then open the file using logisim-evolution.

## Overview

This cpu consists of 4 main registers which hold 8 bits each. (The last bit of each register is a buffer, this applies to the input and output registers as well). It consists of 16 bytes of ram controlled by the memory address manager. The alu allows the cpu to perform addition, subtraction, checking if two numbers are equal, checking if one number is greater than another number. The input consists is limited to 16 lines of code and the output consists of an 8x8 display which displays the result in binary.

## Instruction Register
