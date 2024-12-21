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
![Screenshot 2024-12-21 112052](https://github.com/user-attachments/assets/e5fa8f9b-067b-47e1-a5a6-ab2fe97980cf)

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

![Screenshot 2024-12-21 112125](https://github.com/user-attachments/assets/bd38563a-f4d5-450b-9462-032447c64d52)

**Truthtable**
Full adder
![Screenshot 2024-12-21 112227](https://github.com/user-attachments/assets/3fb444ab-71ed-4888-b10b-36292c013fc5)
Full subractor
![Screenshot 2024-12-21 112406](https://github.com/user-attachments/assets/690d9be4-c921-4ab4-85e2-6f52fd2f8a62)

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.



**Program:**

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by:S.Nandhini
RegisterNumber:24013591
*/
```
Full adder

//full adder
module exp4(sum,cout,a,b,cin);
output sum;
output cout;
input a;
input b;
input cin;

//internal nets
wire s1,c1,c2;


//instantiate logic gate primitives
xor (s1,a,b);
and (c1,a,b);
xor(sum,s1,cin);
and(c2,s1,cin);
or(cout,c2,c1);


endmodule

Full subtractor

module exp4a (df,bo,a,b,bin);
output df;
output bo;
input a;
input b;
input bin;
wire w1,w2,w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(~w1&bin);
assign df=^bin;
assign bo=w2|w3;
endmodule
```

**RTL Schematic**
Full adder
![Screenshot 2024-12-21 112630](https://github.com/user-attachments/assets/6228f6f7-3b6c-4b36-aa8f-28ecb044adaf)
Full subractor
![Screenshot 2024-12-21 112717](https://github.com/user-attachments/assets/ed7ea49b-c75b-4825-82a0-4e35eba9b3dc)


**Output Timing Waveform**
Full adder
![Screenshot 2024-12-21 112745](https://github.com/user-attachments/assets/f7f4b135-f280-41f9-a0c2-109fb9d5e96e)
Full subractor
![Screenshot 2024-12-21 112842](https://github.com/user-attachments/assets/345b642c-35fa-4fc6-bd15-88c30e661346)

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



