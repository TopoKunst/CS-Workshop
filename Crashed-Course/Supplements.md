## Early Computing
    1. Abacus - the earliest calculate instrument. 
    	a. Add and subtract. 
    	b. The development of the scape of the society. 
    	c. 1, 10, 100, 100 .... 
    	d. No need to remember add in the head. 
    2. Step Reckoner - German polymath Gottfried Leibniz in 1694. 
    	a. Multiplication and division. 
    	b. First machine can do all four operations. 
    	c. Problems: 
    		i. Take few days to get the result. 
    		ii. Too expensive. 
    3. Pre-computed Tables 
    	a. Look up the answer instead of using the step reckoner for a few days. 
    4. Difference Engine 
    	a. Could approximate polynomials. 
    	b. Ultimately abandoned. 
    	c. One was constructed by historians in 1991, and it worked. 
    5. Analytical Engine - General Purpose Computer
    	a. Ahead of its time.  
    	b. Never fully constructed. 
    6. Ada Lovelace - English Mathematician, World's First Programmer. 
    	a. Wrote hypothetical programs for the Analytical Engine. 
    7. Tabulating Machine (Electro-Mechanical) - Herman Hollerith. 
    	a. Use punch card to represent data. 
    	b. Helped the US Census. 
    	c. Founded the Tabulating Machine Company, which later merged with other machine makers in 1924 to become the IBM. 

## Electronic Computing 
	1. Harvard Mark I - One of the largest electro-mechanical computers. 
		a. Be built to run simulations for the Manhattan Project. 
		b. Roughly 3000 relays. 
		c. Relays: electrically-controlled mechanical switches. 
		d. Problems 
			i. Slow switching speed. 
			ii. Wear and tear. 
	2. Thermionic Valve - developed by English physicist John Ambrose Fleming in 1904. 
		a. Houses two electrodes inside an airtight glass bulb. 
		b. One of the electrodes could be heated to emit electrons,  the other electrode could then attract these electrons. 
		c. Only positive charged will work. 
	3. Diode 
		a. Electronic components that permits the one-way flow of current. 
	4. Triode Vacuum Tubes - developed by American inventor Lee de Forest.  
		a. Add a third electrode that sits between the two electrodes of valve. 
		b. Positive charge: permit the flow of electrons. 
		c. Negative charge: prevent the flow of electrons. 
		d. No moving parts: faster. 
	5. Vacuum Tubes 
		a. No moving parts, faster than relays and can be used for longer times. 
		b. Marked the shift from electro-mechanical computing to electronic computing. 
	6. Colossus MK 1 - the first large-scale use of vacuum tubes for computing. 
		a. Was used to decrypt Nazi communications. 
		b. 1600 vacuum cubes. 
		c. The first programable electronic computer. 
			i. By plugging hundreds of wires into plugboards. 
	7. ENIACT - The Electronic Numerical Integrator and Calculator, completed in 1946.
		a. World's first truly general purpose, programmable, electronic computer. 
	8. Transistor - Invented by John Bardeen, Walter Brattain, and William Shockley in 1947, Bell Laboratory. 
		a. Semiconductor 
			i. Set between two electrodes. 
			ii. Sometimes can conduct electricity, sometimes resist it. 
		b. Gate electrode 
			i. Manipulate the conductivity of the semiconducting material by changing the electrical charge of the gate. 
		c. Faster, smaller (nowadays smaller than 50 nanometers), and more stable (solid state component). 
	9. IBM 608 - the first fully transistor-powered, commercially-available computer. 
	10. Silicon Valley - Santa Clara Valley, between San Francisco and San Jose, California, named by the most common material used to create semiconductors. 
	11. Shockley Semiconductor - employees later founded Fairchild Semiconductors - employees later founded Intel - the world's largest computer chip maker today. 

## Boolean Logic & Logic Gates 
	1. Binary 
		a. Use two states to represent information. 
		b. 1 / 0, true / false. 
	2. Boolean Algebra 
		a. Values of variables are true and false. 
		b. NOT 
			i. Negate a Boolean value.
		c. AND
			i. Two inputs, one output. 
			ii. If the both inputs are true, the output is true. 
		d. OR
			i. Two inputs, one output. 
			ii. Only one input has to be true for the output to be true. 
		e. Exclusive OR (XOR) 
			i. If both inputs are true, the XOR is false. 

## Representing Numbers and Letters 
	1. Use binary to represent number. 
		a. Add digits to the front. 
		b. Base-two notation. 
		c. 101
			i. 1 four
			ii. 0 two 
			iii. 1 one. 
	2. bit 
		a. One binary digit, 1 or 0. 
	3. Byte 
		a. 1 byte = 8 bits. 
		b. 1 kilobyte = 210 bytes. 
	4. Represent positive and negative numbers 
		a. Use the first bit for the sign. 
		b. Use the remaining 31 bits for the number itself. 
	5. Floating Point Numbers 
		a. IEEE 754 - 32-bit floating point number. 
			i. First bit for the sign of the number. 
			ii. Next 8 bits for the exponent. 
			iii. Remaining 23 bits for the significand. 
	6. Represent Text 
		a. ASCII - the American Standard Code for Information Interchange, invented in 1963. 
			i. 7 bit code, can store 128 different values. 
			ii. Allow different computers made by different companies to exchange data. 
			iii. Limitation only for English. 
				2) Too many characters in Asian languages. 
		b. Unicode - devised in 192. 
			i. 16 bits code, can store over a million values. 

## How Computer Calculate - the ALU 
	1. ALU - Arithmetic & Logic Unit 
		a. Intel 74181 - the most famous ALU. 
			i. The first complete ALU that fit entirely inside of a single chip. 
			ii. Can handle 4-bit inputs. 
			iii. About 70 logic gates. 
			iv. Couldn't multiply or divide. 
		b. An arithmetic Unit 
			i. Half adder
			ii. Full adder 
			iii. 8-bit ripple carry adder 
			iv. Overflow Occurs when the result of an addition is too large to be represented by the number of bits you are using. 
			v. Carry-Look-Ahead adder - faster in modern computers. 
			vi. Operations can be done by the ALU. ADD
				2) ADD with CARRY 
				3) SUBTRACT 
				4) SUBTRACT with BORROW 
				5) NEGATE 
				6) INCREMENT 
				7) DECREMENT 
				8) PASS THROUGH 
		c. The logic union 
			i. Perform logical operations, like AND, OR and NOT. 
			ii. Perform simple numerical tests. 
		d. Flags 
			i. 1-bit code. 
			ii. For particulate states and statuses. overflow 
				2) zero 
				3) negative 

## Registers and RAM 
	1. AND-OR latch 
		b. Gated latch 
	2. Register 
		a. A group of latches. 
		b. Can hold a single number. 
		c. The number of bits in a register is called its width. 
		d. 16 * 16 matrix for 62 bits. 
	3. Memory address 
		a. Multiplexer 
			i. To convert from an address into something that selects the right row or column. 
	5. Random Access Memory 
		a. Can access any memory location, at any time, and in a random order. 

## The Central Processing Union 
	1. Instruction Address Register 
		a. Stores the memory address of the current instruction. 
	2. the Instruction Register 
		a. Stores the current instruction.  
	3. CPU operation (control unit) 
		a. Phase 1 - Fetch Phase 
			i. Retrieve the first instruction. 
		b. Phase 2 - Decode Phase 
			i. Figure out what the instruction is. 
		c. Phase 3 - Execute Phase 
	4. Clock 
		a. Keep the CPU ticking along. 
		b. Trigger an electrical signal at a precise and regular interval. 
	5. Clock speed / Hertz
		a. The speed at which a CPU can carry out each step of the fetch-decode-execute cycle. 
	6. Intel 4004 - the first single-chip CPU, released in 1971. 
		a. 4-bit CPU. 
		b. 740 Kilohertz clock speed. 
		c. Few gigahertz clock speed for todays computer chips. 
	7. Overclocking 
		a. Modify the clock to speed up the tempo of the CPU. 
	8. Underclocking 
		a. Save power. 
	9. Dynamic frequency scaling 
		a. Processors can increase or decrease their clock speed based on demand. 

## Instructions & Programs 
	1. CPU is a piece of hardware which is controlled by easy-to-modify software. 
	2. Software gives hardware capabilities that they cannot do by itself. 
	3. Cannot use 4-bit code represent some value 
		a. variable length instructions 
			i. Make the value longer, but harder to read. 
	4. Intel 4004 
		a. 46 instructions. 
		b. 8-bit immediate values. 

## Advanced CPU Designs 
	1. Make processor faster 
		a. Improve the switching time of the transistors inside the chip. 
		b. Put a little piece of RAM right on the CPU -- called a cache. 
		c. Instruction pipelining. 
		d. Run several streams of instructions at once -- multi-core processor
		e. Use multiple independent CPU. 
	2. Bus 
		a. Wires than transmit data between CPU and RAM. 
	3. Cache 
		a.  a little piece of RAM on the CPU. 
		b. Usually KB or MB. 
		c. Cache hit
			i. Data requested in RAM is already stored in the cache. 
		d. Cache miss 
			i. Data requested in RAM is not already stored in the cache. 
		e. Can always be used to store some middle value. 
		f. Dirty bit 
			i. The place used to record the mismatch between cache and RAM. 
			ii. The dirty bit will be checked before sync. 
				1) If it's dirty, the old data is written back to RAM before loading in the new block. 
		g. Sync will happen when the cache is full but a new block of memory is being requested by the processor. 
	4. Instruction pipelining 
		a. Parallelize the operation. 
		b. Problems 
			i. Data dependencies. 
			ii. Conditional jump instructions. 
		c. Out-of-order execution 
			i. Processor dynamically reorder instructions with dependencies. 
		d. Speculative execution 
			i. When facing a JUMP instruction, advanced CPUs guess which way they are going to go, and start filling their pipeline with instructions based off that guess. 
		e. Superscalar  
			i. Processor that can execute more than one instruction per clock cycle. 
	5. Multi-core processor 
		a. Processors that have several independent processing units inside of a single CPU chip. 

## Early Programming 
	1. Programmable textile loom - developed by Joseph Marie Jacquard in 1801. 
		a. Use punch cards. 
		b. Cheap, reliable, fairly human-readable. 
	2. Plug boards 
		a. Control panels that were full of little sockets into which a programmer would plug cables. 
		b. By the 1920s, these boards were made swappable to make programming more comfortable. 
		c. ENIAC - the world's first general-purpose electronic computer, completed in 1946. 
			i. Use a ton of plug boards. 
			ii. Take up to few weeks to switch programs. 
	3. Stored-program computers 
		a. Store a entire program in the computer memory. 
		b. Can store not only programs, but also data. 
	4. Von Neumann Architecture 
		a. Unifying the program and data into a single shared memory. 
		b. A processing unit containing an ALU, data registers and instruction register and instruction address register. 
		c. A memory to store both data and instructions. 
	5. Punch cards 
		a. Write the contents of the card into the computer's memory. 
		b. Get data out of the computer. 
		c. Punched paper tape 
	6. Panel programming 
		a. Use huge panels full of switches and buttons. 
		b. Indicator lights can display the status of various functions and values in memory. 











































