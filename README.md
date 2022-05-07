# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
~~~
1.Use module projname(input,output) to start the Verilog programmming.
2.Assign inputs and outputs using the word input and output respectively.
3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
4.Use each output to represnt onre for differnce and the other for borrow.
5.End the verilog program using keyword endmodule.
~~~




## Program:
/*~~~
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: sathwik ravuri
RegisterNumber:212220050026
~~~
*/

## HALF SUBTRACTOR

module HalfSubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule

## FULL SUBTRACTOR

module FullSubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule

## Output:

## Half Subtractor:
### Logic Symbol
![1 1](https://user-images.githubusercontent.com/103410316/167242373-13605747-b45d-4cb0-b6b1-150a7673b2fc.png)

### Truthtable
![1 2](https://user-images.githubusercontent.com/103410316/167242380-8bbb737d-1299-4fa5-bbaa-51bb99c48dfe.png)


### RTL realization

![Screenshot 2022-05-05 203043](https://user-images.githubusercontent.com/103410316/167242386-90555d20-10bb-4aee-93bc-e1233327d3c2.png)

### Timing diagram
![halfsubtract  timming](https://user-images.githubusercontent.com/103410316/167242397-5e3e38b0-3667-4b31-9f85-a23bc46be2ac.png)


## Full Subtractor:
### Logic Symbol
![2 1](https://user-images.githubusercontent.com/103410316/167242403-d568e4c1-be8d-4f00-8a3b-94189e96de51.png)


### Truth![2 2](https://user-images.githubusercontent.com/103410316/167242409-9a74f8ee-dd7f-4e8f-baf8-43a9dcd1d84f.png)
table

### RTL realization
![2 3](https://user-images.githubusercontent.com/103410316/167242413-eb5171c2-4a33-482b-8fc3-a6aa1f61cb66.png)

### Timing diagram
![2 4](https://user-images.githubusercontent.com/103410316/167242420-a856ca49-1575-4c4d-8fa5-6fefea88dbac.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
