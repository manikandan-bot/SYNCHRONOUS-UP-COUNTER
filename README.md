### SYNCHRONOUS-UP-COUNTER

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
```
1. Type the program in Quartus software.
2. Compile and run the program.
3. Generate the RTL schematic and save the logic diagram.
4. Create nodes for inputs and outputs to generate the timing diagram.
5. For different input combinations generate the timing diagram.
```

**PROGRAM**
```
Developed by:T.Manikandan
RegisterNumber:24901040
```
***UP counter***
```
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @(posedge clk)
begin
   if (!rstn)
	    out<=0;
	else
	    out<=out+1;
end
endmodule
```

***DOWN counter***
```
module unit11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @(posedge clk)
begin
   if (!rstn)
	    out<=0;
	else
	    out<=out-1;
end
endmodule
```

**RTL LOGIC UP COUNTER**

![Screenshot 2024-12-09 133536](https://github.com/user-attachments/assets/c5a5d5ab-6ce2-470e-81be-eeed03d41376)


![Screenshot 2024-12-09 133627](https://github.com/user-attachments/assets/458013b6-2956-4654-b636-a68e2feefad5)



**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot 2024-12-09 133831](https://github.com/user-attachments/assets/c035befc-277f-4794-9ff1-c49085e65766)



![Screenshot 2024-12-09 133851](https://github.com/user-attachments/assets/9d8e77d6-11b0-43d3-99ab-ada3d60b6ba2)


**TRUTH TABLE**
![Screenshot 2024-12-09 134115](https://github.com/user-attachments/assets/bbb94951-d66e-4bc1-9025-6f70f04423b6)


**RESULTS**
```
Thus the 4 bit synchronous UP Counter and down counter are done and logic diagrams are designed and the truth tables are verified.  
```
