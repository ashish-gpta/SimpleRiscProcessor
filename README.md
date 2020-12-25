# SimpleRisc Processor

"Processor.circ" is a logisim circuit of the SimpleRisc ISA (21 instructions) Processor. It is a single cycle processor which runs all SimpleRisc instructions. It can run any valid SimpleRisc program to give the right outputs (provided the instructions are given in binary/hexadecimal). The processor has an extra feature of displaying any register (even during the execution of the program) using "Display Address" and "Display Register" for the purpose of verification and debugging. The implementation uses 5-stage pipelining and data forwarding.

### How to use the Processsor?

1. Open Logisim and then open the "Processor.circ" file.
2. Right click the instruction memory and select "Edit Contents" and then enter the SimpleRisc program/instructions.
3. All the entered instructions should be encoded (in hexadecimal). You can obtain the encoded form of the SimpleRisc instructions by using the .encode macro of the interpreter.
4. For proper functioning of the program, while entering the instructions, you SHOULD start with the instructions of the .main function. You should also end the .main function with an extra instruction, the unconditional branch with offset 0 (which is encoded as 0x90000000) to stall the processor after successful execution of the program.
5. If you already have a program that had been saved using Logisim's Hex Editor, instead of the above three steps, you can right click the instruction memory, select "Load Image" and open the required saved program.
6. Once the instruction memory is successfully populated with the program, you should set "Clock" to zero and then set "Reset" to one.
7. Then set "Reset" to zero and enable the clock by selecting the "Ticks Enabled" option in the "Simulate" menu in the menu bar (or simply press CTRL + K). You can also adjust the clock frequency using the "Tick Frequency" in the "Simulate" menu.
8. This makes your program run on the processor. You can view the value of any register in hexadecimal while the program is running (or after the program has been executed) using the “Display Address” and “Display Register".
9. Just enter the address of the required register in "Display Address" and its value will be displayed in “Display Register".
10. One can view any sub-circuit (like the register file, control unit, etc.) while the program is running by right clicking the desired sub-circuit and selecting "View <sub-circuit>".
11. The program execution will be completed once the processor reaches the 0x90000000 instruction.
