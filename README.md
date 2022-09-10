# LALU
Arithmetic Logic Unit in Logism. LALU is a 16-bit arithmetic logic unit with hardware multiplication. Addition, Subtraction, and Multiplication handle negative numebrs.
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

| Instsruction | [7:2]     | [1:0] | Format   | Description  |
|--------------|-----------|-------|----------|--------------|
| jump  jmp    | target PC |   00  | jmp targ | PC = targ PC |
