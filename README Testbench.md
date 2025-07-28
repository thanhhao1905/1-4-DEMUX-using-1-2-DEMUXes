```verilog
`timescale 1ps/1ps;
module tb_demux1_4;
  
  reg i;
  reg [1:0] sel;
  wire [3:0] y;
  reg [3:0] exp_y;
  integer err =0;
  integer k;
  
  demux1_4 DUT (i,sel,y);
  
  initial begin
    $monitor ("time=%0t,i=%b,sel=%b,y=%b | exp_y =%b",$time,i,sel,y,exp_y);
    
    for(k=0;k<8;k=k+1) begin
      {sel,i}= k[2:0];
      case (sel)
        2'b00: exp_y = {3'b000,i};
        2'b01: exp_y = {2'b00,i,1'b0};
        2'b10: exp_y = {1'b0,i,2'b00};
        2'b11: exp_y = {i,3'b000};
       default: exp_y = 4'bxxxx;
     endcase
  
  #5;
 check(y[3:0],exp_y[3:0]);
 end
                        
  if(err == 0) begin
  $display("-----------------");
  $display("Test Pass");
  $display("-----------------");
  end else begin
  $display("-----------------");
  $display("Test false with %d error",err);
  $display("-----------------");
  end
  
  $finish;
  end
                        
  task check (input [3:0]y, input [3:0]exp_y);
   begin
   if(y !== exp_y) begin
     $display("[CHECK]: ERROR ");
     err=err+1;
     end else begin
     $display("[CHECK]: Matching ");
     end
   end
 endtask
                            
   initial begin
    $dumpfile("dump.vcd");
    $dumpvars;
    end
endmodule
                        
