# Fast - Reverse Engineering Challenge

## Challenge Information
- **Event:** Fast
- **Category:** Reverse Engineering
- **Author:** SD0
- **Description:** "Think you can read that fast? Think again."

## Overview
This challenge presents an elf file  that displays the flag character by character, but deletes each character too quickly for the human eye to read. The goal is to use debugging techniques to pause the execution at the right moment to capture the flag.

## Initial Analysis
The binary displays the flag characters one by one but removes them at a speed that makes it impossible for humans to read. This suggests that the program is using some form of timing function (like `sleep()`)# Fast - Reverse Engineering Challenge

## Challenge Information
- **Event:** Securinets ISET Zaghouan x D6ATH E9TERS
- **Category:** Reverse Engineering
- **Author:** SD0
- **Description:** "Think you can read that fast? Think again."

## Overview
This challenge presents a binary that displays the flag character by character, but deletes each character too quickly for the human eye to read. The goal is to use debugging techniques to pause the execution at the right moment to capture the flag.

## Initial Analysis
The binary displays the flag characters one by one but removes them at a speed that makes it impossible for humans to read. This suggests that the program is using some form of timing function between displaying and erasing characters.

## Tools Used
- GDB (GNU Debugger) - For setting breakpoints and analyzing the program execution


## Solution Process

### Step 1: Understanding the Program Flow
First, I ran the program to observe its behavior. As expected, it displayed characters too quickly to read.

### Step 2: Disassembling the Binary
I disassembled the binary to locate the main function and understand the program's logic. The key was to find where the program:
1. Displays a character
2. Waits (using a sleep function)
3. Erases the character

### Step 3: Setting a Strategic Breakpoint

  0x0000000000001349 <+352>:   call   0x10a0 <putchar@plt>
   0x000000000000134e <+357>:   mov    rax,QWORD PTR [rip+0x2cbb]        # 0x4010 <stdout@GLIBC_2.2.5>
   0x0000000000001355 <+364>:   mov    rdi,rax
   0x0000000000001358 <+367>:   call   0x10e0 <fflush@plt>
   0x000000000000135d <+372>:   mov    edi,0x3e8
   0x0000000000001362 <+377>:   call   0x10f0 <usleep@plt>
   0x0000000000001367 <+382>:   lea    rax,[rip+0xdca]        # 0x2138
   0x000000000000136e <+389>:   mov    rdi,rax
   0x0000000000001371 <+392>:   mov    eax,0x0
   0x0000000000001376 <+397>:   call   0x10d0 <printf@plt>
   0x000000000000137b <+402>:   mov    rax,QWORD PTR [rip+0x2c8e]        # 0x4010 <stdout@GLIBC_2.2.5>
   0x0000000000001382 <+409>:   mov    rdi,rax
   0x0000000000001385 <+412>:   call   0x10e0 <fflush@plt>
   0x000000000000138a <+417>:   add    DWORD PTR [rbp-0x38],0x1
   0x000000000000138e <+421>:   mov    eax,DWORD PTR [rbp-0x38]
   0x0000000000001391 <+424>:   cmp    eax,DWORD PTR [rbp-0x34]
   0x0000000000001394 <+427>:   jl     0x1333 <main+330>
   0x0000000000001396 <+429>:   mov    edi,0xa
   0x000000000000139b <+434>:   call   0x10a0 <putchar@plt>
   0x00000000000013a0 <+439>:   mov    eax,0x0
   0x00000000000013a5 <+444>:   mov    rdx,QWORD PTR [rbp-0x8]
   0x00000000000013a9 <+448>:   sub    rdx,QWORD PTR fs:0x28

After analyzing the disassembly, I identified the critical point in the program where it pauses between displaying and erasing characters.
 0x0000000000001362 <+377>:   call   0x10f0 <usleep@plt>
 This was at address: between displaying and erasing characters.

## Tools Used
- GDB (GNU Debugger) - For setting breakpoints and analyzing the program execution


## Solution Process

### Step 1: Understanding the Program Flow
First, I ran the program to observe its behavior. As expected, it displayed characters too quickly to read.

### Step 2: Disassembling the Binary
I disassembled the binary to locate the main function and understand the program's logic. The key was to find where the program:
1. Displays a character
2. Waits (using a usleep function)
3. Erases the character

### Step 3: Setting Breakpoint
After analyzing the disassembly, I identified the critical point in the program where it pauses between displaying and erasing characters. This was at address:    0x0000000000001362 <+377>:   call   0x10f0 <usleep@plt>

steps to solve it :
gdb ./fast

1)disass main
2)break main
3)run
4)b*0x0000000000001362
5)c
and the flag will be displayed letter by letter 






