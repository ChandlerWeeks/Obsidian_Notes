SIMD architectures can improve performance by exploiting DLP, are are more energy efficient than MIMD, since one instruction can perform the same operation on multiple data elements; SIMD also allows programmers to continue to think sequentially, and in many cases, can be exploited automatically. 

# Vector Architectures
- Include instruction set extensions to support vector (1d vector) operations, which are deeply pipelined.
	- Vector instructions operate on vector registers, each of which is a fixed length bank of registers;
	- Data is transferred between vector registers and memory;
	- each vector operation takes vector registers or a vector register and a scalar as input.
- Vector architectures are only effective in apps with DLP;
- **Advantages**:
	- Reduce instruction fetch bandwidth
	- Reduces execution time by eliminating loop overhead, stalls only occur on first vector element, & vector operations are performed in parallel. 

# RISC-V With Vector Operations
- RISC-V has a vector extension where;
- 32 vector registers exist, where each element in each vector register is at most 64 bits wide. 
- There are additional read & write ports on the register file;
- Each vector functional unit can start a new operation on each clock cycle. 
- Processor still needs to detect structural and data hazards
- Vector loads/store units are also pipelined so that one word can be transferred between vector registers and memroy on each cycle after an initial latency.
- Processor still includes a set of scalar registers. 

Modern vector architectures support caching, but tradionally they did not. 

# Forwarding
*Chaining* allows the results of one vector operation to be userd as input to another vector operation. 
A *convoy* is a set of vector instructions that can potentially execute together. Only structural hazards cause separate convoys as true dependences are okay