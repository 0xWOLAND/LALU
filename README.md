![image](https://user-images.githubusercontent.com/41707552/189495720-741b75c7-e7d1-4767-9202-37f5dfc8ddd5.png)
# LALU
Arithmetic Logic Unit in Logism. LALU is a 16-bit arithmetic logic unit with hardware multiplication. Addition, Subtraction, and Multiplication handle negative numebrs. LALU also saves register contents to RAM and has 'if' and '!if' conditionals. Loops are available using jmp and jmpn. The mult.txt file will produce a series of square numbers.  ***Note the LALU is in the FullAdderWithStaticCarry.circ file.
### Components
- IR Decoder  (Decodes the 8-bit instruction)
- Program Counter
- Read/Write Control (regWE)
- Overflow Check
- Carry Look-Ahead Adders

##### Instruction Set
| Instsruction       | [7:6] | [5:4] | [3:0] | Format     | Description         |
|--------------------|-------|-------|-------|------------|---------------------|
| add                |   Rd  |   Rs  |  0010 | add Rd,Rs  | Rd = Rd + Rs        |
| subtract  sub      |   Rd  |   Rs  |  0011 | sub Rd,Rs  | Rd = Rd - Rs        |
| loadImmediate  ldi |   Rd  |  val  |  1110 | ldi Rd,val | Rd = val            |
| load  ld           |   Rd  |   Rs  |  1111 | ld  Rd,Rs  | Rd = data[Rs3:0]    |
| move mov           |   Rd  |   Rs  |  0110 | mv  Rd,Rs  | Rd = Rs             |
| store  st          |   Rd  |   Rs  |  1011 | st  Rd,Rs  | data[Rs3:0] = Rd    |
| multiply mult      |   Rd  |   Rs  |  0110 | mult Rd,Rs | Rd = Rd * Rs        |

| Instsruction | [7:2]     | [1:0] | Format    | Description            |
|--------------|-----------|-------|-----------|------------------------|
| jump  jmp    | target PC |   00  | jmp targ  | PC = targ PC           |
| jumpn jmpn   | target PC |   01  | jmpn targ | PC = targ PC if Rd < 0 |
**Clarification for jmpn: If the previously used register has a value < 0, then jmpn actls like jmp (it is a 'if not' statement)
### Assembler
- Mult.py converts the instruction program to hex, which is put into the RAM on the left side of the LALU file. 
- 
