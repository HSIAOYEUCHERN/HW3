# HW3

voter design :
```
module voter_case_design (I, O);
  input [3:0] I;
  output [3:1] O;
  reg [3:1] O;
  
always@ (I)
  case(I)
    4'b0000: O = 3'b100;
    4'b0001: O = 3'b100;
    4'b0010: O = 3'b100;
    4'b0011: O = 3'b010;
    4'b0100: O = 3'b100;
    4'b0101: O = 3'b010;
    4'b0110: O = 3'b010;
    4'b0111: O = 3'b001;
    4'b1000: O = 3'b100;
    4'b1001: O = 3'b010;
    4'b1010: O = 3'b010;
    4'b1011: O = 3'b001;
    4'b1100: O = 3'b010;
    4'b1101: O = 3'b001;
    4'b1110: O = 3'b001;
    4'b1111: O = 3'b001;
  endcase  
endmodule
```
voter testbench :
```
module voter_case_tb;
  reg [3:0] I_tb;
  wire [3:1]O_tb;
  voter_case_design decoder_1(.I(I_tb), .O(O_tb));
initial begin
  #0 I_tb = 4'b0000;
  #10 I_tb = 4'b0001;
  #10 I_tb = 4'b0010;
  #10 I_tb = 4'b0011;
  #10 I_tb = 4'b0100;
  #10 I_tb = 4'b0101;
  #10 I_tb = 4'b0110;
  #10 I_tb = 4'b0111;
  #10 I_tb = 4'b1000;
  #10 I_tb = 4'b1001;
  #10 I_tb = 4'b1010;
  #10 I_tb = 4'b1011;
  #10 I_tb = 4'b1100;
  #10 I_tb = 4'b1101;
  #10 I_tb = 4'b1110;
  #10 I_tb = 4'b1111;
  #10 $finish;
end
  
initial begin
  $dumpfile("voter_case.vcd");
  $dumpvars(0, decoder_1);
end
endmodule
```
![image](https://user-images.githubusercontent.com/101077336/166140738-5698f582-b984-4840-a5e5-08d124754541.png)
