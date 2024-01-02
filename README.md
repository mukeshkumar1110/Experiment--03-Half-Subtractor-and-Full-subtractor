# Developed by: Mukesh Kumar S
# Register Number: 212223240099

# EXP-04 Half-Subtractor-and-Full-subtractor

## Aim:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime

## Theory:
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

### Half Subtractor:
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)

Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

### Full Subtractor:
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure:
1.Use module projname(input,output) to start the Verilog programming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire, assign and required logic gates to represent the boolean expression.

4.Use each output to represent one for differnce and the other for borrow.

5.End the verilog program using keyword endmodule

## Program:
Program to design a half and full subtractor circuit and verify its truth table in quartus using Verilog programming.
````
module halfsub(a,b,difference,borrow);
input a,b;
output difference,borrow;
assign difference = (a^b);
assign borrow = (~a&b);
endmodule

module fullsub(a,b,c,difference,borrow);
input a,b,c;
output difference,borrow;
assign difference=(a^b^c);
assign borrow=(~a&(b^c)|(b&c));
endmodule
````

## Output:

### Truthtable:
#### Half Subtractor:
![image](https://github.com/RoopakCS/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139228922/65c7a4da-ca15-47a5-9cc0-59b6a935a254)
#### Full Subtractor:
![image](https://github.com/RoopakCS/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139228922/fceed04d-7396-4c11-ad78-693d661ab24b)

### RTL realization:
#### Half Subtractor:
![halfsub](https://github.com/RoopakCS/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139228922/6e310e09-5875-4c5f-b8bc-2b1ba3b23a6e)
#### Full Subtractor:
![fullsub](https://github.com/RoopakCS/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139228922/fd0ae8e0-61d5-4cd7-b44a-51a8742aea81)

## Timing diagram:
#### Half Subtractor:
![Half Subtractor Waveform](https://github.com/RoopakCS/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139228922/25cdda2d-5017-4a18-b93e-94336dc2811a)
#### Full Subtractor:
![Full Subtractor Waveform](https://github.com/RoopakCS/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/139228922/ca38da30-8705-4a04-a44d-7ceb1c7acae2)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
