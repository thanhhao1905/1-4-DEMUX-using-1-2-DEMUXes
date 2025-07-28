```verilog
module demux1_2 (input wire i,
                 input wire sel,
                 output wire [1:0] y);
  assign y= sel ? {i,1'b0}:{1'b0,i};
endmodule


module demux1_4 (input wire i,
                 input wire [1:0] sel,
                 output wire [3:0] y);
  wire [1:0] z;
  
  demux1_2 d1(i,sel[1],z);
  demux1_2 d2(z[1],sel[0],{y[3],y[2]});
  demux1_2 d3(z[0],sel[0],{y[1],y[0]});
endmodule
