
# NAME:PRADEEP V
# REG NO:212223240119
# EX-11 SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:PRADEEP V 
RegisterNumber:212223240119
*/

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

**RTL LOGIC UP COUNTER**
![325158164-480f6713-e7c6-45a1-a3b5-711f776877aa](https://github.com/velupradeep/SYNCHRONOUS-UP-COUNTER/assets/150329341/eb77cb31-76b7-47c3-be89-1deef42c13a1)


**TIMING DIAGRAM FOR IP COUNTER**
![325158306-93adb12a-57dd-47be-9f71-6b194b5f8b0f](https://github.com/velupradeep/SYNCHRONOUS-UP-COUNTER/assets/150329341/200de07c-0ea1-444c-a447-a492a165c62b)

**TRUTH TABLE**
![325158378-21e30059-c5dd-41e0-9606-c4f9ee721544](https://github.com/velupradeep/SYNCHRONOUS-UP-COUNTER/assets/150329341/e5f17247-1f9e-4870-92b2-eb11ed61af0e)


**RESULTS**
 Hence a 4 bit synchronous up counter is implemented correctly
