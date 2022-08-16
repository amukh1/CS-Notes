# My CS Notes

## Introduction to how computers work:

Computers are awesome.

Computers store data in the form of numbers, But unlike humans, they do not have fingers.

So how do they count? Well, computers have something called ***transistors***. Transistors have ***two*** states. "On" or "Off".

You can image "Off" as 0, and "On" as 1.

Then how do computers count past 1?

Humans have 10 fingers, so we count using a base 10 number system.

Computers have a base 2 number system, Called ***binary***.

This is the number "One" in 4-bit binary. **0001**

<br>

### Binary:
<br>
You can imagine each "Digit" or "Bit" in a binary number has a Value of either 0 or 1, and a Worth.

<br>

| Number: | 0 | 0 | 0 | 1 |
|:------|:------|:------|:------|:------|
| Value: | 0 | 0 | 0 | 1 |
| Worth | 8 | 4 | 2 | 1 |

<br>

You can see the worth increases by a factor of 2 each time. That is why binary is a ***base 2*** number system.

If the value is 0, then we dont add the worth to the final number.

If the value is 1, then we add the worth to the final number.

Since the value for the worth "1" is 1, we add 1 to the final number.

None of the other values are 1, so we dont add anything to the final number.

We end up with the number 1 as our final number.

<br>

| Number: | 0 | 1 | 0 | 1 |
|:------|:------|:------|:------|:------|
| Value: | 0 | 0 | 0 | 1 |
| Worth | 8 | 4 | 2 | 1 |

<br>

This is 5.

You can see the value for the worth 1 is 1, so we add 1 to the final number.

The final number is now 1.

You can also see the value for the worth 4 is 1, so we add 4 to the final number.

The final number is now 5.

All the other values are 0.

We are left with the number 5.


### Now you can read binary numbers.

<br>

## ROM and RAM:

<br>

ROM: Read Only Memory.

RAM: Random Access Memory.

You can read **and** write to RAM.

RAM is a computer's memory, It is used to store data.

ROM can only be **read** from, so usually it is used to store the main program of the computer, like the operating system.

ROM and RAM both store **BINARY** data.

A computer has **Opcodes**, which stand for "Operation codes".

An example of an opcode is "ADD", which adds two numbers.

Opcodes are encoded in binary though, so each binary number has an opcode associated with it.

For example, if you designed a CPU, you might say "0001" is the ADD opcode.

Storing "0001" and 2 other binary numbers in a rom slot on that specific CPU would make the CPU add those numbers.

That is an example of a very primitive program humans used to write, we would have levers that represented 0 and 1, and the CPU would read them as binary.

Humans dont like to program in binary though, so we invented ***ASSEMBLY***.

<br>

## Assembly:

<br>

With assembly, instead of writing "0001" and then 2 numbers, we would write "ADD" and then 2 numbers.

So now, we could write programs in english, and then translate them to binary.

Assembly is still really hard to write, because it is still just a bunch of functions the cpu can do.

Simple tasks like printing a message to the "Standard Output" (the terminal/screen) take way more lines than modern programming languages.

In Javascript, we can write a program that prints "Hello World" to the screen in 1 line of code.

```javascript
console.log("Hello World");
```

In assembly, we would write:

```asm
section	.text
	global _start       ;must be declared for using gcc
_start:                     ;tell linker entry point
	mov	edx, len    ;message length
	mov	ecx, msg    ;message to write
	mov	ebx, 1	    ;file descriptor (stdout)
	mov	eax, 4	    ;system call number (sys_write)
	int	0x80        ;call kernel
	mov	eax, 1	    ;system call number (sys_exit)
	int	0x80        ;call kernel

section	.data

msg	db	'Hello, world!',0xa	;our dear string
len	equ	$ - msg			;length of our dear string
```

<br>

### **looks hard.. right?**

<br>

Yeah, a complicated program in assembly would be thousands of lines more than a modern language.

Its good to understand it though, we use things called "Compilers" to "Compile" our modern code into assembly, and then "Assemblers" to "Assemble" the assembly into machine code.

<br>

In a way, everything comes down to assembly. Everything your write in a "High-Level Language" (Modern language) is translated to assembly at some point.

Assembly is considered a "Low-Level Language", Because it is on a level that is "Closer" to the CPU, since its intructions are directly ran by the CPU.

Javascript, for example, is a "High-Level Language", because it is a "Farther" from the CPU, But it is still translated to assembly at some point.

<br>

## Computer Architecture:

<br>

## Registers:

<br>

Registers store immediate data, that we can use to perform operations on.

For example, you cannot multiply two numbers directly from RAM, first you move both bits of data into two different registers, and then you multiply them, **THEN** you move the result back into **ANOTHER REGISTER**.

So we move data into registers to perform operations on them, and the result is stored in another register.

<br>

## The Stack:

<br>

Imagine a stack of plates.

Each plate has data in it.

If you "PUSH" to the stack, you are putting a plate to the top of the stack, from a register.

Then that plate is stored there, until you "POP" it off the stack, into a new register.

You can't just grab a plate from the middle of the stack, because the plates are stacked on top of each other.

You can only put a plate on the top of the stack, and then take it off the top of the stack.

If you keep Pushing plates on the top of the stack without Popping, you will eventually run out of room, and that is called a "Stack Overflow".

<br>

## The "Heap":

<br>

The "Heap" is a large area of memory that is used to store data.

When you store data in the "Heap", you get a "**Return Address**" back.

You can use this "**Address**" to access the data in the "Heap".

Similar to the stack, you must clean up the data in the "Heap" after you are done with it, otherwise you will have a "**Memory Leak.**" This is reffered to as "**Garbage Collection**".

<br>

## To be continued..
