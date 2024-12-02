# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

**Full Adder**

![full-adder-truth-table](https://github.com/user-attachments/assets/43f491be-b330-4423-a75b-24de8afb1217)

**Full Subtractor**

![full-subtractor-truth-table](https://github.com/user-attachments/assets/63503d8c-6780-444a-a2db-88bf31d2fc95)

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**Program:**

**Full Adder**
```
//full adder 
module exp4a(sum,cout,a,b,cin);
output sum;
output cout;
input a,b,cin;

//internal nets
wire s1,c1,c2;

//instantiate logic gate primitives
xor(s1,a,b);
and(c1,a,b);
xor(sum,s1,cin);
and(c2,s1,cin);
or(cout,c2,c2);

endmodule
```
**Full Subtractor**
```
module exp4b(df,bo,a,b,bin);
output df,bo;
input a,b,bin;
wire w1,w2,w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(~w1&bin);
assign df=w1^bin;
assign bo=w2|w3;
endmodule
```
/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 
Developed by: Dhanvant Kumar V
RegisterNumber: 24005057
*/

**RTL Schematic**

**Full Adder**
![exp4a](https://github.com/user-attachments/assets/5b2d960a-154e-4358-87b3-4b1e62afc396)

**Full Sutractor**
![exp4b](https://github.com/user-attachments/assets/1b1c78a2-a145-4ce1-9fdd-42ef24feb346)

**Output Timing Waveform**

**Full Adder**
![Waveform result screenshot 4a](https://github.com/user-attachments/assets/086fd38d-e4d4-490d-bf68-9220823cbaab)

**Full Subtractor**
![Waveform result screenshot 4b](https://github.com/user-attachments/assets/8c13d677-c9b9-4f5d-a528-c17683ea7ead)

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



