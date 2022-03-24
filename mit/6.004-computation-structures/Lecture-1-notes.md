L01: The Digital Abstraction

#Computers evolved a bunch in 70y
70 y ago computing devices were
- 30 ton, 200kW, ~1000 operations/sec

now (2018) computers are much faster
- 1Kg, 10W, 10 billion ops/sec

a lot of compute capability and its growing quickly
progress in computer hardware, enalbes new classes of systems
in turn transforming computer science as a whole.

# Intro to Digital World
## Main course roadmap
We'll bridge the gap from computer hardware, transistors and stuff to computer programs.
Abstraction 0: Bits, Logic Gates
Module 1: Digital Design: combinational and sequential circuits.
Abstraction 1: Digital Circuits
Module 2: Computer Architecture: Learn Assembly, processor, caches, pipelining
Abstraction 2: Instruction set + memory
Module 3: Computer Systems: Operating Systems, virtual memory, I/O
Abstraction 3: Virtual machines

these abstractions is what makes possible to have the massive growth whiles still beign able to
handle the massive growth that hardware has been having.

problems with abstraction?
Abstractions may be not enough to handle modern stuff, design choices are inherited

Our focus: Programmable General-Purpose Processors
- Microprocessors are basic building blocks for computer systems
- Microprocessors most sophisticated
- Methodology to learn by doing

Use modern design Tools
Programming circuits in "Bluespec"

compile designs -> into simulated circuit

Course stuff - gotta check what I can take from the site.
there is the online material for the same course but from 2017 and by accessing
6004.mit.edu there is a bit of free resources there (no login required) that may help as well

# Digital Abstraction
Systems that process and manipulate date in a cheap, efficient and robust way.
2 types of systems, analog and digital.
Analog: continuous systems representing real world info (voltage, temperature, pressure...)
Digital: process information usingg discrete symbols, typically binary symbols (bits), encoded using
ranges of smt physical (eg. voltage)
Digital Systems tolerate noise! Are robust vs noise.

## Noise is fundamental problem with any analog system. Makes outputs messy and unreliable.

World isn't actually digital, so there still might have manufacturing problems and some noise that
can affect our digital systems. Just smt to keep in mind.

## Using voltage Digitally
Using 2 voltage ranges is not the best idea, because values near the threshold value would be
difficult to evaluate.
The solution to this may be have 2 separate ranges and a gap between these 2 ranges. But the problem
may persist because values near the Lower threshold (for ex.) may still be influenced by noise and
therefore be wrongly informed.
To solve this problem we'll make a voltage range that is able to handle the noise.
Noise margins.
Analog -> noise accumulates at each stage.
Digital -> noise can be cancelled at each stage. (using transistors, capacitors and inductors)

## Vol, Vil, Voh, Vol
these are basically the thresholds for:
 - Vol: Valid Output Lower (threshold) - maximum possible output value to generate a "0"
 - Vil: Valid Input Lower (threshold) - maximum valid/accepted input value to generate a "0"
 - Voh: Valid Input Higher (threshold) - minimum possible output value to generate a "1"
 - Vol: Valid Output Higher (threshold) - minimum valid/accepted input value to generate a "1"
 keep in mind that Vol < Vil < Voh < Vol


## Voltage Transfer Characteristic
It's a tool that let's one observe the (voltage) input and output behavior of a system in a static way.
graph of Vin by Vout, needs to obey the boundaries from upper and lower digital valid inputs

## Types of Digital Circuits
Digital Inputs -> smt -> Digital Outputs
smt = ?
Combinational circuits (lectures 2-5)
 - don't have memory.
 - each output is a function of current input values.
 - AND, OR, NOT, these are all combinational circuts, most know as logic gates.

Sequential circuits (lectures 6-8)
 - have memory (state)
 - each output depends on current input and memory values

# Summary
Digital tolerate noise

Digital enconding
 - valid voltage levels that represent 0 and 1
 - undefined range to avoid mistakes in misinterpreting 0 and 1
 - signal validity is taken into account

Noise margins need to be robuster on outputs more than inputs, because? -> 
The outputs would be more influenced by noise than the input, and since the output may be used
in other inputs, if the output is "filtered" and as clean as possible that mitigates a lot of the
propagation of noise.

# Take-Home Problem
Suppose that you measured the voltage tnrasfer curve of the device shown below. Can we finda
asignaling specification (Vil, Vih, Vol, Voh) that would allow this device to be a digital inverter?
if so, give the specification that maximizes noise margin.
  the graph has the following coordinates
  (0, 5), (1, 4), (2.5, 1), (3, 0.5) and (5, 0.5)

