# Digital Circuits
The fundamental building block of digital logic circuits are digital logic gates. One would implement a simple boolean function (e.g., `NOT`, `AND`, `OR`). 

[TODO: table for `NOT`, `AND`, `OR`, `XOR` boolean notation and schematic]: #
[include notation for bit vectors; slashed line through signal wire with number of bits on top]: #
## Combinational Logic Circuits
This type of circuit has no cycles. That is, the result of the function is not referenced in anyway the next time the function is run. 

One way to describe such a function is with the **sum-of-products** form. It is `AND` statements joined together with `OR`s. To create one, fill out the truth table for the function. For each `1` result, join the value of each input with `AND`s. Finally, join each statement with `OR`s.

[TODO: two-input multiplexer example here]: #
An example of a combinational circuit is the ripple-carry adder. These are chained full adders, each of which comprise of two half adders. A single full adder handles a single position's sum and carryOut. Since there are only two digits, `0` and `1`, if the sum would be `2`, carryOut would become `1` and sum "resets" to `0`. The carryOut of one full adder becomes the carryIn of the next full adder in a ripple-carry adder. Subtraction can be performed with a ripple-carry adder as well; just get the additive inverse of the second argument then set the initial carryIn to `1`.

[TODO: schematic here]: #
The barrel shifter is a way of performing shifts. Let $n$ be the number of bits in the argument, and $d$ the shift amount. This circuit comprises of $\log_2 n$ levels $l$, with each level containing $n$ `MUX2` circuits. The arguments to one of the multiplexers is the following: `MUX2(d[l], 1, 0)`. If true, the bit will go down the wire that shifts $2^l$ positions. Later multiplexers will have a bit `0` pass through in the case a bit did not pass through (i.e., the bit got shifted and needs to be replaced with a `0`).

[TODO: is the `MUX2` argument correct?]: #
[schematic?]: #

## Sequential Logic Circuits
On the other hand, this kind of circuit has at least one cycle. It relies on state, a fixed finite-size "summary" of the history of input sequences to the circuit. The gory details are not recorded in state.

[input or output?]: #
The **set-reset latch** is the basic building block for history. It takes two inputs $R$ and $S$, which correspond to set and reset respectively. The outputs of the circuit are $Q$ and $\bar{Q}$. The definition is as follows:
- If $R$ is `1` and $S$ is `0`, $Q$ is `0` and $\bar{Q}$ is `1`
- If $R$ is `0` and $S$ is `1`, $Q$ is `1` and $\bar{Q}$ is `0`
- If $R$ and $S$ are `0`, latch mode is active: the previous values of $Q$ and $\bar{Q}$ are maintained
- $R$ and $S$ both being `1` is disallowed by design

[TODO: schematic here, 10.3]: #
A **clock** is a binary signal that switches between `0` and `1` each fixed cycle time. The time it takes from turning to one state then returning to it again is known as the *clock cycle time*. This is measured in seconds. Clock frequency can be obtained by taking the reciprocal of the clock period.

[TODO: the weird flip-flop things]: #
A finite-state machine is a form of sequential logic circuit. It has a combinational part that performs the computations. The inputs to the combinational portion are external and also the current state. The outputs are also external and constructs the next state. This "next state" is then looped around to become the "current state" and the cycle repeats. 

FSMs can be categorized. *Acceptors* produce a binary output that indicates whether or not the input is valid. *Transducers* performs calculations based on input and/or state to produce an output. Furthermore, if a transducer only refers to state, it is a *Moore machine*. If input is also needed, it is a *Mealy machine*.