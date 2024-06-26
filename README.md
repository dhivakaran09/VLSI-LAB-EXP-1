# VLSI-LAB-EXPERIMENTS
# AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

# APPARATUS REQUIRED: Vivado 2023.3

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

# Logic Diagram :

# Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


# Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


# Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


# Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



# Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



# 8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



# VERILOG CODE:
# Logic Gates:
```
module logicgate (a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;  
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b); 
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```
# Half Adder:
```
module halfadder(a,b,sum,carry);
input a,b;
output sum,carry;
xor g1(sum,a,b);
and g2(carry,a,b);
endmodule
```
# Half Subractor:
```
module halfsubtractor(a,b,diff,borrow);
input a,b;
output diff,borrow;
xor g1(diff,a,b);
and g2(borrow,~a,b);
endmodule
```
# Full Adder:
```
module fadd(a,b,c,sum,carry);
input a,b,c;
output sum,carry;
wire w1,w2,w3;
xor g1(w1,a,b);
and g2(w2,a,b);
xor g3(sum,w1,c);
and g4(w3,w1,c);
or g5(carry,w3,w2);
endmodule
```
# Full Subtractor:
```
module fs(a,b,bin,d,bout);
input a,b,bin; 
output d,bout;
wire w1,w2,w3;
xor g1(w1,b,bin; 
xor g2(d,w1,a);
and g3(w2,a,~w1);
and g4(w3,~b,bin);
or g5(bout,w2,w3);
endmodule
```
# 8 bit rca:
```
module ripplemod(a, b, cin, sum, cout);
input [07:0] a;
input [07:0] b;
input cin;
output [7:0]sum;
output cout;
wire[6:0] c;
fulladd a1(a[0],b[0],cin,sum[0],c[0]);
fulladd a2(a[1],b[1],c[0],sum[1],c[1]);
fulladd a3(a[2],b[2],c[1],sum[2],c[2]);
fulladd a4(a[3],b[3],c[2],sum[3],c[3]);
fulladd a5(a[4],b[4],c[3],sum[4],c[4]);
fulladd a6(a[5],b[5],c[4],sum[5],c[5]);
fulladd a7(a[6],b[6],c[5],sum[6],c[6]);
fulladd a8(a[7],b[7],c[6],sum[7],cout);
endmodule
```
# module fulladder(a, b, cin, sum, cout)
```
input a;
input b;
input cin;
output sum;
output cout;
assign sum=(a^b^cin);
assign cout=((a&b)|(b&cin)|(a&cin));
endmodule
```

# OUTPUT:
# logic gates
![WhatsApp Image 2024-05-15 at 13 45 00_86147890](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/37b0de92-ca2c-4803-8f0c-cc9f2309b00e)

# and gate
![WhatsApp Image 2024-04-01 at 10 29 41_c2a5c002](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/8a9ffbf8-642c-4995-88fe-7a51cd384ac5)
# or gate
![WhatsApp Image 2024-04-01 at 10 30 27_c6c94d72](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/cf039252-313c-413d-9b14-77a075e48f4e)
# xorgate
![WhatsApp Image 2024-04-01 at 10 31 00_7de75e2e](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/53d04b7f-aa93-4daa-aaf8-2d1381e02431)
# nandgate
![WhatsApp Image 2024-04-01 at 10 31 16_0c4e2605](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/8ba06318-beb0-4087-8f42-74bd5a0f97f4)
# norgate
![WhatsApp Image 2024-04-01 at 10 31 44_5683c233](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/0bfba81d-50f6-466b-99ea-109e2b699a28)
# xnorgate
![WhatsApp Image 2024-04-01 at 10 33 01_75a65e51](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/36e1a5a8-a0b8-40bb-ac45-e0c7addf7856)
# notgate
![WhatsApp Image 2024-04-01 at 10 33 19_dbf4abb2](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/1d09545e-8707-4cc2-8a84-bb0c3a3368e3)
# Half adder
![WhatsApp Image 2024-04-01 at 10 33 36_b1f8f353](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/94a1406a-d501-475f-8987-b10219aee18e)
# Half subtractor
![WhatsApp Image 2024-04-01 at 10 34 36_901bbc71](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/0a297489-5509-4b39-9dd8-4fbfaf360127)
# Full adder
![WhatsApp Image 2024-04-01 at 10 34 57_d103b715](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/b907f9f3-536d-47ee-8597-2b8c522d69ee)
# Full subtractor
![WhatsApp Image 2024-04-01 at 10 35 11_f51630a3](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/39a10198-1901-4058-ac48-e83b2d7f2ad2)
# 8 bit rca
![WhatsApp Image 2024-04-01 at 10 35 28_a3cdae0c](https://github.com/dhivakaran09/VLSI-LAB-EXP-1/assets/164842673/4ae778b6-834c-437c-b713-dbf13ae80af1)



# RESULT:
Hence Logic Gates,Adders and Subtractor are simulated and synthesised using Xilinx ISE.















