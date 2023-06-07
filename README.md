# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic gates
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.
 F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
F2=xy’z+x’y’z+w’xy+wx’y+wxy
 
 
 
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory

 Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. Using NAND gates

NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted. F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms. F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'






## Procedure


The input and output variables are allocated with letter symbols. The exact truth table that defines the required relationships between inputs and outputs is derived. The simplified Boolean function is obtained from each output. The logic diagram is drawn. Program:



## Program:
/*
Program to implement the given logic function and to verify its operations in quartus using Verilog programming.
Developed by: tamizh selvan.R
RegisterNumber: 212222230158 
*/
```
module combine(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(~c & b & a);
assign q=(~d & c & c & a);
assign r=(c & ~b & a);
assign f=(~(~p & ~q & ~r));
endmodule

module combine1(a,b,c,d,f);
input a,b,c,d;
output f;
wire p,q,r;
assign p=(c & ~b & a);
assign q=(d & ~c & a);
assign r=(c & ~b & a);
assign f=((p | q & |r));
endmodule
```
## Output:

## RTL

![241928152-fc4147d5-c983-42bf-8f2b-80b56ad42eef](https://github.com/tamizhselvan1920/Experiment--02-Implementation-of-combinational-logic-/assets/121148386/1d87f3c0-2eab-43c1-b0f4-878b3432d9f1)

![241928256-1310cacb-c695-4738-b235-4fcb5abd9365](https://github.com/tamizhselvan1920/Experiment--02-Implementation-of-combinational-logic-/assets/121148386/feaeb9a7-002c-43b0-ab33-ac5c8491256e)



## Timing Diagram

![241928481-f531d20f-fe20-4c06-97e9-88e64a213854](https://github.com/tamizhselvan1920/Experiment--02-Implementation-of-combinational-logic-/assets/121148386/f5ab2197-3897-49c6-9f54-b82f1b187d73)


![241928566-55651651-bfa1-4c9c-8714-3134eaf16774](https://github.com/tamizhselvan1920/Experiment--02-Implementation-of-combinational-logic-/assets/121148386/027eada1-8780-4dde-8a82-ab0f1762f14a)


## Result:
Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.
