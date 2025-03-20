bistable device: a physical object with two stable—cannot randomly change—states
  using semiconductors (e.g., silicon) in electronics makes making switches easy
    MOSFET = metal oxide semiconductor field effect transistor
      transistors act as a switch by applying physical force
      MOSFET applies voltage to gates to switch between states; source and drain are electrically connected
        cut off: basically no current; gate-to-source voltage is below threshold
        saturation region: current has hit max; drain-to-source voltage is too high
        most basic building block of electronic devices
  ferromagnetic material is another way of achieving a bistable electronic device
    usually seen in hard drive discs
    based on direction of magnetization (stable saturation M-states of the magnetic hysteresis curve)
math definition of modulus
  a = qd + r
    given a and d
  	where 0 < d
  	0 <= r < |d|
  	r = a mod d
  normal for positive
  negative a is: find a multiple of d that is less than or equal to a then find the difference for r
## Word Size
There is a power of 2 number of cells in memory indexed from 0 to 2^w - 1. Each ell holds one byte of data. Memory accesses are always a whole number of bytes. This is called byte-addressed memory. w is called the word size of the machine. w is the number of bits needed to represent the address of a memory cell.
- AArch64 (and x86-64) W = 64
- AArch32 (and IA32) W = 32
## Arithmetic On Representations
There are two results to single-digit addition: sum and carry. These function just as expected, but the divergence occurs when the sum goes beyond the two available digits. The carry is incremented, and the sum goes back to zero and can climb again. 
The half adder is this operation; the sum can be obtained through a `XOR`, and carry with `AND` %%maybe replace with schematic%%. A full adder does the initial half adder then takes the sum of that and the `carryIn` into another half adder to generate the final sum and another `carryOut`. The two `carryOut`s meet at an `OR` to generate the final `carryOut`. Connect multiply full adders by the `carryIn`s and `carryOut`s to create a ripple-carry adder. This allows addition with larger numbers %%do a full adder per bit?%%. Additionally, subtraction can be performed by doing `NOT` on one argument then setting the first `carryIn` to `1` %%is this correct?%%.
%% NEW %%
For floating point, make sure the power on the 2 are the same. This can be done by shifting the significand (including the hidden bit) then performing the opposite (multiply for right shift, divide for left shift) on the power on the 2. Then add and right shift the sum once while incrementing the power on the 2.
%% converting decimals from base-10 to base-2. multiply the decimal representation by 2. when there is a whole 1, make it 0 and continue. when the product is 1.0, stop and go back to the top and record in order the whole part. if the product is a repeat, go back to the original step and indicate repetition. %%
## ISA
System ISA has higher privilege and may only be used by the OS. User ISA by everyone else. The **Application Binary Interface** includes user ISA and system calls (e.g., `sbrk()`). **Application Programming Interface** includes user ISA and high-level language library calls (e.g., `malloc()`).

The von Neumann Architecture has:
- Processing unit
- Control unit: ensure the instructions are being performed and program counter (what is the next instruction)
- Memory
The von Neumann bottleneck is when only an instruction or data can go between the process and memory. This is because there's only one connection. There is also no distinction between instruction and data memory. This comes with the risk of self-modifying code.
The Harvard Architecture fixes these problems by having separate memories of instructions and data and separate connections.
## Code Generation
Local variables are stored in the functions "stack frame." They are some offset from the `SP`. Global variables are at locations that may be accessed via `label`.