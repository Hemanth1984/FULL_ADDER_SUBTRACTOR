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

**Procedure**

Write the detailed procedure here

**Program:**

Full Adder:
```
module fulladd(a,b,c,sum,carry);
input a,b,c;
output sum,carry;
wire[3:1]w;
xor g1(w[1],a,b);
xor g2(sum,w[1],c);
and g3(w[2],a,b);
and g4(w[3],w[1],c);
or g5(carry,w[3],w[2]);
endmodule
```

Full Subtractor:
```
module fullsub(a, b, c, diff, borrow);
input a, b, c;
output diff, borrow;
wire w1, w2, w3;
xor G1(w1, a, b);
xor G2(diff, w1,c);
and G3(w2, ~a, b);
and G4(w3, ~w1, bin);
or  G5(borrow, w2, w3);
endmodule
```

**RTL Schematic**

Full Adder:

<img width="922" height="404" alt="499663890-2d923590-e47b-43bf-8ebe-dd4b250b1f57" src="https://github.com/user-attachments/assets/48acdd28-857d-4a40-836e-e626cc3e6c73" />

Full Subtractor:

<img width="1133" height="536" alt="499663959-82280526-6356-4972-8425-424ebf68f33e" src="https://github.com/user-attachments/assets/1e7e0e5f-937e-4607-be05-c2d1a3f1d30f" />

**Output Timing Waveform**

Full Adder:

<img width="1885" height="513" alt="499664052-e11b6fb8-5d15-4d0c-946d-9b5417c6e44a" src="https://github.com/user-attachments/assets/62945ffc-3293-416f-b919-45a5851f2ce2" />

Full Subtractor:

<img width="1914" height="465" alt="499664131-c6764c3c-b052-4579-8dff-73a023f7895e" src="https://github.com/user-attachments/assets/52a4d0a1-98ca-4923-9bc3-de5c89197721" />

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



