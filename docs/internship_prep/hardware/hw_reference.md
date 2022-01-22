# Hardware Reference

## ASICSs vs FPGAs vs Processors

### ASIC

- High performance
- Low power
- Cheaper for large volumes

### FPGA

- “Instant Manufacturability”
- Cheaper for small volumes

### Processor

- Easy to design (software)
- General purpose

## FPGA Design Process

![FPGA Design Process](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled.png)

FPGA Design Process

![3-input LUT](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%201.png)

3-input LUT

1. Synthesis: break logic into LUTs
    1. $n$ input LUT can make any $n$-input function, combinational or sequential
2. Mapping/placing: place LUTs into CLBs such that
    1. Connected LUTs are close to each other
    2. Critical path is approximately minimized
3. Routing: connecting logic blocks together
    1. Uses programmable switches
        1. NMOS acts as conductor when config bit (part of bitstream) is 1 → connect tracks
    2. Varying segment lengths to connect CLBs that are far or close to each other
        1. Use shorter segment lengths to minimize delays and noise and crosstalk
        2. Longer segments have extra capacitance and limited quantity
4. Timing analysis: looks for timing violations
    1. Path delay is sum of all logic and wire delays 

## SystemVerilog

- Types of modules
    - Behavioral: describe what module does (gate level)
    - Structural: describe how it is built from simpler modules (instantiates other modules)
- Unlike regular Verilog, SystemVerilog supports OOP and generate statements
    - Generate statements are for readability; they don’t change hardware implementation

## Memory

- Types: DRAM (volatile, capacitor), SRAM (nonvolatile, cross-coupled inverter), ROM (nonvolatile, read only)

## Caches

- Temporal (recently accessed in cache), and spatial (multi-word blocks) locality
    - If more temporal, decrease block size and number of sets; increase associativity
    - Instructions more spatial, data both
    - Temporal locality memory mountain: levels, based which level of cache can fully contain working set
    - Spatial locality memory mountain: throughput decreases with increasing stride length until stride length ≥ block size
- Amdahl's law: speed up = 1 / (1-a + a/k), where a is the percentage of sped up code by a factor of k
- associativity: number of cache lines per set
    - increasing associativity decreases conflict misses, but decreases performance (lookup and replacement times)
- Block size: number of bytes per cache line
- Write through is good for synchronization, write back is faster when modifying same cache line multiple times

## Timing

### Gate Delay

- Every wire and transistor has parasitic capacitance (physical property)
- Delay of logic gate is time for it to charge the capacitance on its output
    - Equivalent capacitance of the parasitic capacitances of the wires and transistors
    - Proportional to R*C (n*R*C for n gates, where n is the number of gates in the path)
        - R depends on size of logic gate transistor (bigger → lower R) and length of wire (longer → higher R)
        - C depends on the same things in the same ways as R, but also depends on fanout (larger fanout → higher C, summing for each [parallel] branch)
            - Fanout: number of inputs driven by an output
                - Reduce fanout by splitting net, but this increases the number of gates

### Modelling Delays

- Setup time: how long input needs to be stable before clock edge to be accepted
    - clock period ≥ clk→q max + critical path + setup time
    - Setup violation causes metastability
    - Fix by slowing down clock or moving registers around to reduce length of critical path (i.e. pipelining, which is best when critical path >> other paths)
- Hold time: how long input needs to be stable after clock edge to be accepted
    - clk→q min + fastest path ≥ hold time
    - Hold time violation causes the loss of data
        - Could be caused by clock skew
    - Fix by increasing gate/DFF delays, adding buffers to data path or first clock path

### Old STA Notes - [setup and hold slack](https://asic-soc.blogspot.com/2013/08/setup-and-hold-slack.html)

- Slew rate: rate of change from 0 to 1, or 1 to 0
- Skew: clock signal arrives at different times for different components, fix using buffers
- Setup time: how long input needs to be stable before clock edge to be accepted
    - clock period ≥ clk→q max + critical path + setup time
- Hold time: how long input needs to be stable after clock edge to be accepted
    - clk→q min + fastest path ≥ hold time
    - cannot be fixed by increasing clock period
- Slack: time when it actually happens vs when it must happen (has to happen before must happen, positive slack)
    - setup: required - arrival
    - hold: arrival (clk→q if from register + combo) - required (clock - setup)
- Glitch: short output change when two inputs change simultaneously, i.e., gated clock (use feedback path instead; overlap on kmap)

#### Practical Issues

- Retiming in pipelining: move combinational logic from one side of DFF to another to balance critical path length of each stage
- Clock skew: clock edge arrives at different components at different times (i.e. difference in length of wires)
    - Implications: change in Fmax (changes setup time), failure of design (hold time violations and functional problems like second clock arriving to late loses the current value)
    - Minimize relative skew using
        - H-tree network (route so that same distance to each flop)
        - Global clocks that have dedicated routing to minimize clock skew; however, limited availability
- Phase locked loops: mixed signal circuit that generates output clocks aligned to an input clock
    - Motivation: usually there is clock skew between the input and output clocks of a clock divider/multiplier, and routing a generated clock is unpredictable
    - Can even generate output clocks with the same phase as input clock

### Glitches

- Glitch: undesired short-lived pulse that occurs before a signal settles to its intended value
- Caused by unequal arrival times of inputs on combinational gates + same output is generated by different values of state bits
    - For example, XORing the bits 01 → 0, transitioning to 11 or 00 → 1 before settling at 10 → 1
    - Any transition consumes power, so unnecessary transitions consume unnecessary power

#### Glitches in FSMs

- Effects
    - Edges triggered inputs (i.e. clocks) may be falsely triggered
    - Enables may glitch before being sampled, causing garbage to be read
    - Hard to detect
- Avoiding glitches
    - Try to make it so that only 1 input bit changes at a time
    - Register next outputs
        - Quick fix, but adds one cycle delay, does not support direct dependence of outputs on inputs, requires extra registers
    - Eliminate combinational logic after state machine
        - Move before current state machine or next state machine
    - Require outputs to either be
        - Driven from a state bit or its complement
        - Driven by (simple) combinatorial logic that depends on a single state bit (safest for signals that are constant for the duration of the state machine's operation)

### Clock Domain Crossings

- Clock domain: all DFFs in each clock domain are clocked by the same clock
- Signals that cross clock domains will likely cause timing violations
    - Asynchronous signals also cause timing violations in a similar manner
- On a timing violation, output may get the right value, wrong value, or become metastable (value between 0 and 1 that resolves randomly) → may cause system-wide failure

#### Metastability

- If the time it takes for a metastable node to resolve is greater than setup slack (negative slack), then system failure
- $MTBF(t_{slack})=\frac{e^{t_{slack}/C_0}}{C_1f_{CLK}f_{DATA}}$
    - Average time between two failure-causing instances of metastability
    - Increases exponentially with slack
    - Maximize by synchronizing asynchronous inputs

### Slack

- Time when it actually happens vs when it must happen (has to happen before must happen, positive slack)
- setup slack: required - arrival
- hold slack: arrival (clk→q if from register + combo) - required (clock - setup)
- required time: clock path
    - Reg to reg and input to reg: Tclock - Tsetup
    - Reg to output: unconstrained
- arrival time: data path
    - Reg to reg and reg to output: Tclk-q + Tcombo
    - Input to reg: Tcombo
- Reference: [ASIC-System on Chip-VLSI Design: Setup and hold slack (asic-soc.blogspot.com)](https://asic-soc.blogspot.com/2013/08/setup-and-hold-slack.html)

## Arithmetic Circuits

### Adders

- 1-bit adders: half adder (2 input, 2-bit output), full adder (adds carry in bit to half adder)

#### Multibit Adders (Carry propagate adders)

- Ripple-carry (slow): chain of full adders that bitwise add N-bit inputs; $t_{ripple} \approx Nt_{FA}$
    - $t_{FA}$ is the delay of a full adder
    - Delay proportionate to N
    - FPGAs optimized for ripple carry adders, so faster than other implementations with N ≤ 16
- Carry select (less slow): calculate high-order bits for both cases of carry-in, select correct case when carry in is available
    - Requires more hardware, but faster
- Carry-lookahead (fast): compute carry out for k-bit blocks using generate and propagate signals
    - $G_i = A_iB_i$
        - $G_{3:0} = G_3+P_3(G_2+P_2(G_1+P_1G_0))$
    - $P_i = A_i+B_i$
        - $P_{3:0} = P_3P_2P_1P_0$
    - $C_{out} = G_{in} + P_{in}C_{in}$
    - Delay of 4 bit adder: 4 gates
        
        ![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%202.png)
        
        - All generate and propagate bits ready in 1 gate
        - All carry bits ready in 2 gates (AND OR network)
        - Sum input and carry bits (same as XOR) in 1 gate
    - Not very scalable, so typical to make a 32-bit CLA out of 4-bit CLAs
        1. Compute all $G_i,P_i$
        2. Compute all $G,P$ for each 4-bit block
        3. $C_{in}$ propagates through each block
        
        ![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%203.png)
        
        ![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%204.png)
        
        - Thus $t_{CLA} = 4log_4(N)t_{PD}$ (proportional to logN)

### Miscellaneous Arithmetic Circuits

- Subtractor: take two's complement of second input
- Equality comparator: AND all the bitwise XORs
- Less than comparator: subtractor; last (sign) bit is 1 when A < B
- Shift less than: all 0's, except LSB is result of less than comparator (A < B)
- Arithmetic shifters (`<<<` `>>>`) are the same as logical shifters (`<<` `>>`) except the right arithmetic shift is sign extended
- Division: most complex, always use multi-cycle dividers in practice

### Multipliers

- Multiplication is a complex operation: avoid if possible
    - Add instead of multiply: 7*2 → 7+7
    - Shift instead of multiply (power's of 2): 7*2 → 7 << 2
- 1-bit x N-bit: AND operation
- N-bit x N-bit: sum of shifted 1-bit X N-bit for each bit in the second term (same as multiplication by hand)
- Large multipliers: constructed out of smaller N-bit x N-bit multipliers
    - 2N-bit x 2N-bit produces 4N-bit result
    - $2^N, 2^{2N}$ terms in equation shift are shift lefts

![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%205.png)

![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%206.png)

- Signed multipliers: subtract last number (two's complement) rather than add it
- Serial (multi-cycle) multiplier
    
    ![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%207.png)
    

## Decimal Numbers

### Fixed Point

- Base 2, N-bit representation: m integer bits (m<n), n-m fraction bits
- Arithmetic operations: align decimal, perform as usual
    - Multiplication and division result in loss of precision

### Floating Point

![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%208.png)

![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%209.png)

- Binary scientific notation: (±1.m * 2^e → sign * 1.mantissa/significand * base^exponent)
- Purpose of bias is to circumvent the need for a signed exponent field
- 64-bit: 1 sign bit: 11 exponent bits: 52 fraction bits, bias is 1023
    - Largest positive: exponent is all 1s except LSB, mantissa is all 1s
    - Smallest positive: exponent is all 0s except LSB, mantissa is all 0s
- Special cases
    - Subnormal: exponent all 0s, mantissa is interpreted as being preceded by 0
        - Smallest positive: mantissa is all 0's except LSB
        
        ![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%2010.png)
        

### Fixed vs Floating Point

- Fixed: simpler circuitry → cheaper, smaller, less power consumption
- Floating point: higher dynamic range of representable values
    - Not synthesizable unless explicitly accounted for; useful for simulation

## Power Optimization

### Types of Power

![Untitled](Quick%20Reference%2099f7f99436be4200b1da42666f1af893/Untitled%2011.png)

- As digital circuits shrink (and voltage of chips decrease)
    - Dynamic power decreases (V and C decrease in dynamic power equation)
    - Static power of new chip is a higher proportion of total power (decreasing dynamic power and increasing leakage current)

### Reducing Power Consumption

- Custom chip
    - Turn off regions that are unused to reduce static power (dark silicon)
    - Multiple threshold libraries
- FGPA
    - Minimize area (less leakage, may allow for smaller FPGA)
- General
    - Lower voltage
    - Revise implementation (add instead of multiply, invert bus)
    - Pipelining (adding flip flops prevents glitches from propagating → reduce glitch power)
        - Disadvantage: flip flops use power, extra burden on clock tree
