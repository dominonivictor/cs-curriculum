# Combinational Devices and Boolean Algebra

Combination Devices
all of these is a static discipline:
- has 1 or more digital inputs
- has 1 or more digital outputs
- functional specification (what it does)
- timing specification (worst case scenario from valid input to valid output) = propagation delay

a set of interconnected elements is a combinational device if:
- each circuit element is combinational
- everey input is connected to exactly one output or a constant (0 or 1)
- the circuit doesn't contain a directed cycle

-some examples-
any combinational function can be mapped to a Boolean expression or truth table

Boolean Algebra:
- 2 elements, 0 and 1
- 2 binary operators, AND (.) and OR (+)
- one unary operator, NOT (overbar or !)

3 axioms:
- identity => a.1 = a <> a+0=a
- null => a.0 = a <> a+1 = 1
- negation => !0 = 1 <> !1 = 0

Duality principle: If a valid truthfull boolean expression, then replacing
0 with 1 and AND with OR yields another expression that is truthfull

Using axioms we derive several usefull other expressions to simplify and manipulate boolean
expressions

- commutative => a.b = b.a <> a+b = b+a
- associative => a.(b.c) = (a.b).c <> a+(b+c) = (a+b)+c
- distributive => a.(b+c) = a.b+a.c <> a+b.c = (a+b).(a+c)
- complements => a.!a = 0 <> a+!a = 1
- absorption*^* => a.(a+b) = a <> a+a.b = a
- reduction*^* => a.b + a.!b = a <> (a+b).(a+!b) = a
- DeMorgan's Law => !(a.b) = !a + !b <> !(a+b) = !a.!b
*^* => very used to optimize circuits used for minimal parts

# Equivalence and Normal Form
unique representation using boolean algebra what your function does, but there are ways to simplify.

How to turn them into combinational circuits?
basic logic gates representation... 
AND (flat back, curved front)
OR (curved back, pointy front)
NOT (triangle with circle in front)

Gates are universal, can create any combination possible.
minimal sum-of-product -> expression that reduces a boolean expression to the minimum amount of AND
and OR operators
there are more sophisticated tools to solve big expressions (K-maps)
other method is Multi-Level Boolean Simplification

## Logic Optimization 
Synthesis tool takes:
- High lvl circuit specification
- Standard cell library (set of gates and their physical characteristics, 4 gate AND, 8 gate OR, etc)
- Optimization goals (area/delay/power)

and outputs:
- an optimized circuit implementation (using standard cell library gates)

other used gates
XOR (Exclusive OR) = !a.b + a.!b
NAND (not and) = !(a.b)
NOR (not or) = !(a+b)

## Standard Cell Library
Library gates and physical characteristics
ex: 
| Gate | Delay (ps)| Area (micro^2) |
| Inverter | 20  | 10 |
| Buffer   | 40  | 20 |
| AND2     | 50  | 25 | 
| NAND2    | 30  | 15 |
| OR2      | 55  | 26 |
| NOR2     | 35  | 16 |
| AND4     | 90  | 40 |
| NAND4    | 70  | 30 |
| OR4      | 100 | 42 |
| NOR4     | 80  | 32 |

obs: higher num of inputs higher delay and area
inverting logic is faster and smaller (NAND and NOR is preffered)

# Takeaways
It's a complex problem:
- boolean simplification
- mapping to cell libraries with many gates
- multidimensional tradeofss (e.g., minimize area-delay-power product)

Unfeasible to do by hand for any largerish circuit

Tool used is a hardware description language with a synthesis tool to derive optimized
implementations

# Take home problem

1. Find a minimal SOP expression for following boolean expr.:

A.!B.!C + A.!B.C + !A.!B.C + !A.B.C

2. Using the gates in slide #22(table under Standard Cell Library), find an implementation of this minimal SOP that minimizes area
