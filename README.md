# aim
To simulate and synthesis ripple carry adder using vivado 2023.2

# apparatus
vivado 2023

# procedure
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table

# RIPPLECARRYADDER
![image](https://github.com/RESMIRNAIR/RIPPLECARRYADDER/assets/154305926/62459000-90cb-4c43-a221-7b8cf1d419b0)
![image](https://github.com/RESMIRNAIR/RIPPLECARRYADDER/assets/154305926/24ea1940-0b55-4f8a-be6a-a7ac5daf2919)
# Full Adder
![image](https://github.com/RESMIRNAIR/RIPPLECARRYADDER/assets/154305926/3208d46f-2fd4-4d6a-987f-63102c173ca0)

# verilog code
module  ha (a,b,s,c);
input a,b;
output s,c;
xor g1(s,a,b);
and g2(c,a,b);
endmodule
module fa(a,b,c,sum,carry);
input a,b,c;
output sum ,carry;
wire w1,w2,w3;
xor g1(w1,a,b);
xor g2(sum,w1,c);
and g3(w2,w1,c); 
and g4(w3,a,b);
or g5(carry,w2,w3);
endmodule
module mul_4_bit(x,y,z);
input [3:0]x,y;
output [7:0]z;
wire [17:1]w;
and(z[0],x[0],y[0]);
ha hal (x[1]&y[0],x[0]&y[1], z[1],w[1]);
fa fal (x[2]&y[0],x[1]&y[1],w[1],w[5],w[2]);
fa fa2 (x[3]&y[0],x[2]&y[1],w[2],w[6],w[3]);
ha ha2 (x[3]&y[1],w[3],w[7],w[4]);
ha ha3 (w[5], x[0]&y [2],z[2],w[8]); 
fa fa3 (w[6],x[1]&y[2],w[8], w[12], w[9]);
fa fa4 (w[7],x[2]&y[2],w[9],w[13],w[10]);
fa fa5 (w[4],x[3]&y[2],w[10],w[14], w[11]);
ha ha4 (w[12], x[0]&y[3], z[3], w[15]);
fa fa6 (w[13],x[1]&y[3],w[15],z[4],w[16]);
fa fa7 (w[14],x[2]&y[3],w[16], z[5],w[17]);
fa fa8 (w[11],x[3]&y[3],w[17],z[6],z[7]);

endmodule

 # output
 
![Screenshot 2024-03-16 110410](https://github.com/lathika024/RIPPLECARRYADDER/assets/165888553/53c4c677-666e-493f-ad27-57f454718b21)
# result
thus the ripplecarry adder is verifed successfully using vivado 2023.2
