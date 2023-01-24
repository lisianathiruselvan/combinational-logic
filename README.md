# combinational-logic\

Experiment--04-Implementation-of-combinational-logic-using-universal-gates


Implementation of combinational logic using universal-gates

AIM:

To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate

Equipments Required:

Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime

Theory

Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.

Using NAND gates

NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

Logic Diagram

Using NOR gates NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

Logic Diagram

Procedure
```
Step 1: Create a project with required entities.
Step 2: Create a module along with respective file name.
Step 3: Run the respective programs for the given boolean equations.
Step 4: Run the module and get the respective RTL outputs.
Step 5: Create university program(VWF) for getting timing diagram.
Step 6: Give the respective inputs for timing diagram and obtain the results.
```
Program:

Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.

Developed by: lisiana t

RegisterNumber: 22006964

USING NAND OPERATION
```
module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R;  
assign P = C&(~B)&(~A);  
assign Q = D&(~C)&(~A);  
assign R = (~C)&B&(~A);  
assign F = (~P&~Q&~R);  
endmodule  
```
USING NOR OPERATION
```
module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R,S;  
assign P = C&(~B)&A;  
assign Q = D&(~C)&A;  
assign R = C&(~B)&A;  
assign S = ~(P|Q|R);  
assign F = ~S;  
endmodule 
```
Output:

RTL

FOR NAND



![nandrtl](https://user-images.githubusercontent.com/119389971/214304325-e9d94cf0-b95e-4e72-8c32-6dd626a50695.png)

FOR NOR

![norrtl](https://user-images.githubusercontent.com/119389971/214304344-420e9329-84a6-4434-a40f-03b79380459e.png)

Timing Diagram

FOR NAND
![nandtd](https://user-images.githubusercontent.com/119389971/214304382-93262be6-0185-4da1-9307-d09496a9537d.png)


FOR NOR

![nortd](https://user-images.githubusercontent.com/119389971/214304437-02d9869f-e858-4063-b1ed-55dd0c9313bd.png)

Truth Table

FOR NAND

![nandtt](https://user-images.githubusercontent.com/119389971/214304484-5a745008-b19f-4e5d-b7cf-7cef99a8c70e.png)

FOR NOR

![nortt](https://user-images.githubusercontent.com/119389971/214304518-e41ccba9-def7-4064-8588-1f0d96395e57.png)

Result:

Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
