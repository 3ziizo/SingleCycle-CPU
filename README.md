# Single-Cycle-CPU   

<h3 align="center">Using the Logisim simulator to model and test the processor</h3>
A RISC processor that has seven 32-bit registers: R1 to R7. Register R0 is hardwired to zero. Reading R0 always returns the value 0. Writing R0 has no effect. The value written to R0 is discarded.   
All instructions are 16-bit long and aligned in memory. The PC register contains the instruction address. 

### There are three instruction formats, R-format, I-format, and J-format as shown below:
 **- R format:**   
5-bit opcode (Op), 3-bit register numbers (a, b, and d), and 2-bit function field f   

 **- I format:**   
5-bit opcode (Op), 3-bit register numbers (a and b), and 5-bit Immediate   

 **- J format:**   
5-bit opcode (Op) and11-bit Immediate   

### Register Use:
Register a is the first source register number. Ra is the name and value of register a. It is always read and never written.   
Register b is the second source register number. It is always read in the R-format but can be read and written in the I-format. Rb is the name and value of register b.   
Register d is the destination register number for the R-format only. It is always written and never read. Rd is the name and value of destination register d.

### Instruction Description:
Opcodes 0 and 1 are used for R-format ALU instructions. There are 8 instructions in total.

Opcodes 4 through 15 are used for I-format ALU instructions. Register b is the destination register. The immediate constant replaces the second ALU operand.

The I-format ALU instructions ANDI through SLTI have identical functionality as their corresponding R-format instructions (AND through SLT), except that the second ALU operand is an immediate constant and the destination register is Rb (not Rd).

There are four shift and rotate instructions: SLL to ROR with opcodes 12 to 15. The shift or rotate amount is the 5-bit immediate Imm5 with values 0 to 31. 

There are four branch instructions BEQ to BGE with opcodes 16 to 19 and PC-relative addressing. If the branch is taken then PC = PC + Imm<<1. Otherwise, PC = PC + 2. As with ALU I-format instructions, Branch instructions can use the IMM extension to increase the branch target address range.




