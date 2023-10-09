![LALU-of-FullAdderWithStaticCarry](https://user-images.githubusercontent.com/41707552/189496216-2e7a850e-0524-4512-8d1f-3782aec70535.gif)
<figcaption align = "center"><b>Square Number Series Alternating Between Negative and Positive</b></figcaption>

# LALU
Arithmetic Logic Unit in Logism. LALU is a 16-bit arithmetic logic unit with hardware multiplication. Addition, Subtraction, and Multiplication handle negative numbers. LALU also saves register contents to RAM and has 'if' and '!if' conditionals. Loops are available using jmp and jmpn. The mult.txt file will produce a series of square numbers flipping between the negative and positive values for each value in the sequence.  ***Note the LALU is in the FullAdderWithStaticCarry.circ file. and the 7-Segment Output is in Hex not Decimal
### Components
- IR Decoder  (Decodes the 8-bit instruction)
- Program Counter
- Read/Write Control (regWE)
- Overflow Check
- Carry Look-Ahead Adders

### Instruction Set
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
- Mult.py converts the instruction program to hex
- Put the outputted hex into the RAM input on the left side of the LALU file. 
