# DEVELOP-A-VERILOG-CODE-FOR-THE-DECADE-COUNTER

A decade counter, also known as a mod-10 counter, it is a digital circuit that counts the number of pulses or clock  signals it receives, incrementing its output by one for every ten input pulses. 

The design of a decade counter  typically involves flip-flops, which are basic memory elements in digital electronics.

# VERILOG CODE:


module decade_counter(en, clock, count); 

input en, clock;  

output reg [3:0] count; 

always @( posedge clock) 

    begin 
    
      if(en)  
      
        begin 
       i
       f ( count>=4’d0 && count<4’d10) 
       
         count<=count+4’d1; 
         
         else 
         
          count<=4’d0;  
        en
        d 
      el
      se  
      
        count<=4’d0; 
    end 
    
endmodule 



# TEST BENCH:



`timescale 1ns/1ps 

module decadecounter_tb; 

wire [3:0] count; 

reg en,clock; 

decade_counter dut(.en(en), .clock(clock), 

.count(count)); 

initial begin 

$display($time, " << Starting the Simulation >>"); 

    en=0; 
    
    clock=0; 
   #
   20 en=1'd1; 
end


  always 
  
    #5 clock=~clock;  
  in
  itial 
  
    $monitor ( $time , "clock= %b, count= %d, en= 
%b",
clock,count, en); 

endmodule 





# RTL CODE:  

 
module decoder_counter(clk, rst, q);  

input clk, rst; 

output [3:0]q; 

reg [3:0]q;  

reg clkdiv; 

reg[22:0] div; 

initial q = 4'd0; 

always @ (posedge clk ) 

begin 

div=div+1'd1; 

clkdiv=div[22];  

end 

always@(posedge clkdiv or posedge rst) 

begin 

if (rst == 1'd1) 

q = 4'd0; 

else if (q== 4'd9) 

q = 4'd0; 

else 

q=q+1; 

end  

endmodule 

 
# (Advance ) Verilog Code of Decade Counter : 

module decade_counter ( output reg [3:0] q, 

input clk ); 

always @(posedge clk) 

q <= q = = 9 ? 0 : q + 1; 

endmodule



# PIN ASSIGNMENT: 

 
clock: set_location_assignment PIN_P11 -to CLOCK_50 

rst: set_location_assignment PIN_C10 -to SW[0] 

q[3]: set_location_assignment PIN_A8 -to LEDR[0] 

q[2]: set_location_assignment PIN_A9 -to LEDR[1] 

q[1]: set_location_assignment PIN_A10 -to LEDR[2] 

q[0]: set_location_assignment PIN_B10 -to LEDR[3]


# CONCLUSION:

In conclusion, the decade counter project exemplifies the effective use of Verilog and FPGA technology 
in digital design. The design and implementation of a decade counter using Verilog and FPGA highlight the 
synergy between hardware description languages and reprogrammable hardware platforms. 
