# RISC-V
Table of Contents

Abstract
1.Introduction about RISC-V
2.RV32I Instruction Set
3.Codes
4.Hardware implementation
5.Future Plans

List of Figures
Page No.
Figure 1: 7
Figure 2: 10

				 Abstract
Processors have become one of the most basic needs due to their usage in electronic gadgets and variety of other applications. Most of the popular Instruction Set Architectures are proprietary and require licensing to use them. Currently RISC-V is the best open-source ISA available to researchers, developers and professionals.
In this study, we explore the architecture of RISC-V in depth. Key versions of RISC-V like RV32I (base integer instruction set) have been examined. Other extensions have been dealt on surface level. For RV32I, Different types of registers and their uses and instruction sets have also been covered. Hardware implementations of RV32I like bus based, network on chip, and point to point interconnect. This paper also contains the future scope of our project such as compiler design.

Chapter 1:
INTRODUCTION
The RISC-V (Reduced Instruction Set ) is an open-source instruction set architecture (ISA). It was created at University of Berkley, California to facilitate architecture research and education. This project was led by computer scientists Krste Asanović, Yunsup Lee, and Andrew Waterman. Recently it has garnered immense popularity because of its modularity, extensibility and customizable nature. Developers and professionals can create processors which are catered to specific applications for maximum efficiency and performance. Due to its customizability and flexibility, it has been adopted in different industries.
History and evolution of RISC-V:
Most of the traditional available ISAs required licensing fees and were under the control of very few companies which ensured less competition and more monopoly in the processor market for these companies. Also there was lack of transparency and restrictions on the usage of ISAs. This lack of transparency proved to be an obstacle in academic research in computer architecture.
Many popular and efficient RISC processors (like MIPS) were available before RISC-V but they too needed licensing fees and were not fully transparent about their blueprint.
This led Dr. Krste Asanović and his team to develop an ISA which is transparent and does not require licensing fees. Hence RISC-V came into existence.

			Chapter 2: 
32-bit RISC-V Instruction Format:

R-type Instructions: Register type instructions in the Risc V architecture are used for arithmetic and logical operations between registers.
Eg :- Add rd, rs1, rs2
Funct7(7 bits) :- Function code that together with funct3, specifies the exact operation.
rs2(5 bits) :- Address of the second source register.
rs1(5 bits) :- Address of the first source register.
Funct3(3 bits) :- Function code that together with funct3, specifies the exact operation.
rd (5 bits) :- Address of the destination register where the result is written.
op code(7 bits) :- Specifies the type of operation (eg. Arithmetic , logical)
Some Examples of R-Type Instructions are ADD, SUB, SLL(Shift Logical Left),SRL(Shift Logical Right),SLTU,XOR,SRA)(Shift Arithmetic Right),OR,AND.
OP-CODE FOR R-types (0110011)
I-type Instructions:
I - type instructions or Immediate instructions are used for operations involving an immediate value, These instructions typically perform arithmetic and logical operations where one operand is a constant and other is register.
rs1(5 bits) :- Address of the first source register.
Imm[11:0]:- 12 bits value to store immediate value.
Funct3(3 bits) :- Function code that together with funct3, specifies the exact operation.
rd (5 bits) :- Address of the destination register where the result is written.
op code(7 bits) :- Specifies the type of operation (eg. Arithmetic , logical)
Some Examples of I-type Instructions are ADDI, SLTI ,SLLI , SRLI, SRAI, LI
OP-CODE for I-type Instructions are 0000011.
B-type Instructions:
B type instructions in Risc V are used for conditional branching. They compare two registers and branch to a specified instruction if the comparison is true. B-type instructions use a specific instruction format that include fields for op-code, source registers, the branch target offset and the comparison function.
rs1(5 bits) :- Address of the first source register.
Imm[11:0]:- 12 bits value to store immediate value.
Funct3(3 bits) :- Function code that together with funct3, specifies the exact operation.
rd (5 bits) :- Address of the destination register where the result is written.
op code(7 bits) :- Specifies the type of operation (eg. Arithmetic , logical)
Some Examples of B-type Instructions are BEQ, BNEQ , BLT, BGE, BLTU, BGEU
OP-CODE for I-type Instructions are 1100011.
U-type Instructions:
U-type(Upper Immediate) instructions in Risc-V are designed to work with very large immediate values. These instructions operate on a 32-bit register and involve loading or adding a 20-bit immediate value to either a register or the (PC). The U-type format allows for the manipulation of the upper 20 bits of a register, with the lower 12 bits typically set to zero or used for offset.
Eg:- LUI(Load Upper Immediate),AUIPC(Add Upper Immediate to PC).
OP-CODE (0110111)

J-type Instructions:
Jump instructions in RISC-V are used to alter the flow of execution by setting the PC to a specified address. These instructions can be unconditional (Jump) or conditional, allowing the execution of a different code path based on certain conditions.
Eg:- JAL(JUMP and Link), J(Jump), JALR(JUMP and Link Register)

Register sets:
RISC-V has 32, 32-bit integer registers.
zero (x0):
Hardwired to zero.
Reads always return zero and writes are ignored.
ra (x1): return address register.
Used to store the return address for function calls.
Helps in managing function call stacks and returns.
sp (x2): stack pointer register.
Points to the top of Stack.
Essential for managing stack operations, local variables and function call management.
gp (x3): global pointer register.
Points to the global data section.
Facilitates access to the global variables and constant.
tp (x4): thread pointer register.
Used in multi-threaded programs to point to thread-specific data.
Helps in efficient thread management.
t0-2 (x5-7): temporary registers.
Used for temporary data storage during computations.
Not preserved across function calls.
a0-a7 (x10-17): argument registers.
Used for passing arguments to functions.
Also used for returning values from functions.
s0-s11 (x8, x9, x18-27): saved registers.
Used for pressing data across function calls(callee-saved).
t3-6 (x28-31): temporary registers.
Used for temporary data storage during computations.
Not preserved across function calls.
RISC-V has 32, 32-bit floating registers.
Floating-point temporaries(ft0-7): f(0-7)
Temporary variables.
Floating- point saved registers(fs0-1): f(8-9)
Saved Variables
Floating- point arguments/return values(fa0-1): f(10-11)
Function Arguments/Used to store the return address for function calls.
Floating- point arguments(fa2-7): f(12-17)
Used for passing arguments to functions.
Also used for returning values from functions.
Floating- point saved registers(fs2-11): f(18-27)
Used for pressing data across function calls(callee-saved).
Floating-point temporaries(ft8-11): f(28-31)
Used for temporary data storage during computations.
Not preserved across function calls.

ISA extensions:
RISC-V has a modular design, consisting of alternative base parts, with added optional extensions. All the extensions of ISA base including it are developed as a collective effort between industry,Research Community and educational institutes. The Base provides us with instructions (and their encoding), control flow, registers (and their sizes), memory and addressing, logic (i.e., integer) manipulation, and auxiliaries (or supplements). With base alone we can implement a simplified general-purpose computer, with full software support, including a general-purpose compiler.
In Some RISC-V computers to reduce power consumption, code size, and memory use we might implement compressed extensions too. Researchers are planning to support Hypervisors (software to create and manage Virtual Machines(VM’s)) and virtualization.
Together with the supervisor extension, S, an RVGC instruction set, which includes one of the RV base instruction sets, the G collection of extensions (which includes "I", meaning that the base is non-embedded), and the C extension, defines all instructions needed to conveniently support a general purpose operating system.
RISC-V ISA has a set of extensions which has specific utility for specific applications.
M-extension (RV32IM): Integer multiplication and division extension.
A- extension (RV32IMA): Atomic extension for atomic memory operations.
F-extension (RV32IMAF): Single-precision floating-point operations.
D-extension (RV32IMAFD): double-precision floating-point operations.
C, V, B, Q, L, J, T, P, N etc. are various other types of extensions.

Chapter 4: Hardware implementation
we have three options , bus based , network on chip , point to point interconnect.
a) Bus based Implementation:
In this architecture, various units of the cores share a common 32-bit bus through which they communicate. Control signals determine which components get to use the bus during a particular clock cycle.

A bus based datapath for RISC-V (http://inst.eecs.berkeley.edu/~cs152/sp12)

Enable signal: enable signal is implemented using tri state buffer , used to select which component will use bus
4 enable signals : “enImm”, “enALU”, “enReg” and “enMem”. “enLmm” and “enALU” are directly connected , while “enReg” and “enMem” are used in complex ways. If no enable signal is high then the bus will float.
Special register: bus based has 4, 32 bit edge triggered special registers with enable control : IR(ldIR) , A(ldA) , B(ldB) , MA(ldMA). If a register’s enable is asserted during a particular cycle, then the value on the bus during that cycle will be copied into the register at the next clock edge
If more than one signal is asserted then the bus value will be loaded in all registers whose load signals are arrested.
RegWr and MemWr are also load signals.

Pros: simple to design and implement, low cost, good for small scale systems like embedded systems.
Cons: high latency, limited bandwidth and scalability.

B) Network on chip : mainly used for multi core design , in this implementation , we arrange the different cores in a grid like fashion.

4x4 ESP tile grid with 2 processor, 2 memory, 11 accelerator, and 1 auxiliary tile([2206.01901] Enabling Heterogeneous, Multicore SoC Research with RISC-V and ESP)
Pros: highly scalable , acceptable latency , suitable for many cores.
Cons: very complex , costly.

C) Point to point interconnect: as name suggest , there is dedicated links between different components

Point to Point interconnect(Example of 4-processor setup with point-to-point (QPI-like)... | Download Scientific Diagram)
Pros: low latency , high bandwidth , power efficient
Cons: costly , complex , unfeasible for large system

Chapter 5: Future Scope
Software: Can integrate custom made backend with the front end of gcc compiler in next semester.

Hardware: Will try to design a bus based simple and basic Risc-V hardware using Verilog and implement it on FPGA.

Simplistic View of Design Flow:-
Design Idea
Behavioral Design(I/O - O/P)
Data Path Design(Netlist of register transfer level)
Logic Design (Logical optimization techniques to obtain low cost effective design)
Physical Design(Generate the final layout (testbench) and fabrication)
Manufacturing(FPGA Integration)
Chip/Board (Final output).

