# 8 bit cpu

## Table of Contents

- [How to View](#How_to_View)
- [Brief Overview](#Overview)
- [Instruction Register](#Instruction_Register)
- [registers](#Registers)
- [ALU](#ALU)
- [Mover](#Mover)
- [RAM_and_Memory Address manager](#RAM_and_Memory_Address_Manager)
- [Program Counter](#Program_Counter)
- [Input](#Input)
- [Output](#Output)
- [Assembly](#Assembly)
- [Example Assembly Code](#Example_Code)

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

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image12.png?raw=true" width="350" />

## Program_Counter

The program counter controls the execution of the statements of code written in binary from the input. It first moves binary instruction from the input to the execution register and then executes the instruction. 

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image13.png?raw=true" width="350" />

It also executes the if statement. which checks the output in the specified register and then moves to the specified line. The lines are numbered from 0 to 15. 

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image14.png?raw=true" width="350" />

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image15.png?raw=true" width="350" />

## Input

An input consisting of 16 lines is connected to the cpu through the program counter. 

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image16.png?raw=true" width="500" />

## Output

The output consists of 8x8 matrix of leds which can be written to from the data stored in the registers. It is connected to the registers through the output control

Output Control:

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image17.png?raw=true" width="350" />

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/image18.png?raw=true" width="550" />

## Assembly

Commands can be given to the cpu using binary commands, the instructions of these commands can be directly translated into assembly code as follows. 

- 0000 mov Rd value
- 0001 set Rd adress
- 0010 add Rd Ra Rb
- 0011 sub Rd Ra Rb 
- 0100 and Rd Ra Rb
- 0101 or  Rd Ra Rb
- 0110 get Rd address
- 0111 shw Rx
- 1000 not Rd Ra
- 1001 xor Rd Ra Rb
- 1010 equal Rd Ra Rb
- 1011 greater_than Rd Ra Rb
- 1100 if Rd line_1 line_2 ( if Rd == 1 then program counter goes to line 1 else to line 2 )
- 1101 clear_screen

Rd refers to the destination register. It is the register that the output of the function is moved into. The values of Rd can be from 0 to 3.

The "value" refers to number we want to store in the specified register. 

Ra and Rb refer to the register from which the operands are taken from. the values of Ra and Rb have to be distinct from that of Rd. They can also take values from 0 to 3.

"set" is a function to move the value of a register into the ram. 

"address" refers to the position in the ram we want to store the data in. it can take the values from 0 to 15.

"get" is a function that moves the data stored in the address to the specified register.

For the "set" and "get function the specified register from which and into which the data is transferred will be also be refered to as the destination register.

"if" is a command that can be used to control the flow of statements. If the value contained in the specified destination register is not 0 then the execution will shift to line_1 otherwise it will shift to line 2. The lines are numbered from 0 to 15.

"shw" is the function which prints out the value of a specified register onto the 8x8 display.

"clear_screen" is a function used to clear the 8x8 output. It sets all the bits of the 8x8 display to 0. It must be used in the beginning of the program if and only if the "shw" function is being used in the program at any point.

**The assembly code used here is not the same as the assembly code used in arm or x86 architechture.**

## Example_Code

### Example 1: Building a pyramid and then clearing the screen

This program makes a pyramid and then clears the screen.

**Code in assembly:** 
```
clear_screen
mov R0 1
mov R1 1
shw R0
add R2 R0 R1
mov R1 1
add R0 R1 R2
set R0 1110
get R1 1110
mov R2 11111111
equal_to R3 R2 R0
if R3 line_3 line_0
```

**Code in binary:** 

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/code_for_pyramid.png?raw=true" width="350" />

**Output of the code:**

*The rightmost bit of each line below does not represent the binary code it is used as a buffer as mentioned above*

Link of a video showing the output: [https://www.youtube.com/watch?v=i_A018K-mIY](https://www.youtube.com/watch?v=i_A018K-mIY)

### Example 2: printing the multiples of 5

This program outputs the multiples of 5 lesser than 128 (2^7 = 128).

**Code in Assembly:**

```
clear_screen
mov r0 00000101
mov r1 00000101
shw r0
add r2 r1 r0
set r2 0000
get r0 0000
mov r2 10000000
greater_than r3 r2 r0
if r3 line_3 line_0
```

**Code in binary:**

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/code_for_multiples5.png?raw=true" width="350" />

**Output for the code**

<img src="https://github.com/emaadhakeem07/8bit_cpu/blob/main/img/output_multiples5.png?raw=true" width="350" />

Link of a video showing the output: [https://www.youtube.com/watch?v=5MgjI-cHRFg](https://www.youtube.com/watch?v=5MgjI-cHRFg)
