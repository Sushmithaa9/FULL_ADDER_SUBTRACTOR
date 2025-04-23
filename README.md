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

![WhatsApp Image 2025-04-23 at 14 02 25_60acca3c](https://github.com/user-attachments/assets/fd774b1f-d9fd-4ab6-85e2-7bbc7dd98652)

![WhatsApp Image 2025-04-23 at 14 02 25_1088451a](https://github.com/user-attachments/assets/bd7ba1fa-ccef-4995-99a2-d8e1cb79a128)


**Program:**

Developed by: S MANO SUSHMITHA 
RegisterNumber:212224040187

```
module fulladder(a, b, c, sum, carry);
    input a;
    input b;
    input c;
    output sum;
    output carry;
	 reg sum,carry;
	 reg t1,t2,t3;
	 always @ (a or b or c) begin
	 sum = (a^b)^c;
	 t1=a & b;
	 t2=b & c;
	 t3=a & c;
	 carry=(t1 | t2) | t3;
	 end
endmodule

module fulsubbehavioral(a, b, cin, diff, borrow);
    input a;
    input b;
    input cin;
    output diff;
    output borrow;
	 reg t1,t2,t3;
	 reg diff,borrow;
	 reg abar;
	 always @ (a or b or cin) begin
	 abar= ~ a;
	 diff = (a^b)^cin;
	 t1=abar & b;
	 t2=b & cin;
	 t3=cin & abar;
	 borrow=(t1 | t2) | t3;
	 end
	endmodule

```


**RTL Schematic**


![WhatsApp Image 2025-04-23 at 14 02 24_f65376a5](https://github.com/user-attachments/assets/bd1362b1-37b7-4fd7-8db9-f22308a4af40)


![WhatsApp Image 2025-04-23 at 14 02 24_3beb5a2e](https://github.com/user-attachments/assets/28b13201-281f-4ada-8dec-8d1e4b869bbe)



**Output Timing Waveform**


![WhatsApp Image 2025-04-23 at 14 02 24_71a7874f](https://github.com/user-attachments/assets/1fb9cd4c-1350-4bba-b355-8bf44cb1f1c9)


![WhatsApp Image 2025-04-23 at 14 02 24_1b4ab41c](https://github.com/user-attachments/assets/d0b03c91-d196-440a-bb57-9fcdbf6adc01)



**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



