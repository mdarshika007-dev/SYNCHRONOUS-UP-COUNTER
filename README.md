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

1.	Type the program in Quartus software.

2.	Compile and run the program.

3.	Generate the RTL schematic and save the logic diagram.

4.	Create nodes for inputs and outputs to generate the timing diagram.

5.	For different input combinations generate the timing diagram.

**PROGRAM**
~~~
UP COUNTER:
module day15(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule

DOWN COUNTER:
module day20(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out-1;
end
endmodule 
~~~
Developed by: RegisterNumber:25017631

**RTL LOGIC UP COUNTER**
UP COUNTER:

<img width="1920" height="1080" alt="Screenshot (80)" src="https://github.com/user-attachments/assets/a13b39a2-d384-4be4-9dda-fcd21a3511b6" />


DOWN COUNTER:
<img width="1920" height="1080" alt="Screenshot (82)" src="https://github.com/user-attachments/assets/89314671-86c3-4e0f-a484-8b670153f584" />


**TIMING DIAGRAM FOR IP COUNTER**
UP COUNTER:

<img width="1920" height="1080" alt="Screenshot (81)" src="https://github.com/user-attachments/assets/e5ab43b4-e83f-46f0-bfc5-863b1c37c2ec" />

DOWN COUNTER:
<img width="1920" height="1080" alt="Screenshot (83)" src="https://github.com/user-attachments/assets/3e4e2cfd-a0f7-4431-8cd4-f64da9c4dba8" />

**TRUTH TABLE**
<img width="544" height="275" alt="image" src="https://github.com/user-attachments/assets/b22feea6-fc34-4f0d-8d7c-4db36e7e4193" />

**RESULTS**

Thus the Synchronous 3 bit Up counter and 3 bit Down counter are implemented and verified
