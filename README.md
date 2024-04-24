### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

!![image](https://github.com/RehanJeyan2/SYNCHRONOUS-UP-COUNTER/assets/167837130/ae89fa5f-2dc4-4b19-b880-5b1866191ab8)



![image](https://github.com/RehanJeyan2/SYNCHRONOUS-UP-COUNTER/assets/167837130/9450a251-8389-499d-9363-a9298e1eed8c)


Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */

**PROGRAM**
```
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:Rehan Jeyan
RegisterNumber: 212223220030
*/

**RTL LOGIC UP COUNTER**
![image](https://github.com/RehanJeyan2/SYNCHRONOUS-UP-COUNTER/assets/167837130/b06f0e07-ac45-4568-9743-6ba19d1d7860)



**TIMING DIAGRAM FOR UP COUNTER**
![image](https://github.com/RehanJeyan2/SYNCHRONOUS-UP-COUNTER/assets/167837130/cc3d4e46-2c7e-427c-893b-7d9105f9c7b6)



**TRUTH TABLE**
![image](https://github.com/RehanJeyan2/SYNCHRONOUS-UP-COUNTER/assets/167837130/b0a709d4-b1c4-4b07-bb48-6560f103d063)


**RESULTS**
Hence a  4 bit synchronous up counter is implemented correctly 
