# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
1.Open a new project using Quartus II. 2.Declare the inputs and outputs inside module projname(). 3.Set the reset value using register. 4.Use commands like begin and end to stimulate the counter. 5.For Up counter increment the count and for Down counter decrement the count. 6.End the verilog programming.



### PROGRAM 
Using Up-Counter:
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: vinush.cv
RegisterNumber: 22001897
module up_c(clock,reset,upcounter);
input clock,reset;
output reg[2:0] upcounter;
always@(posedge clock or posedge reset)
begin
if(reset)
upcounter=3'b 000;
else
upcounter=upcounter+1;
end endmodule
```
Using Down-Counter:
```
module do_wn(clock,reset,downcounter);
input clock,reset;
output reg[3:0] downcounter;
always@(posedge clock or posedge reset)
begin
if(reset)
downcounter=4'b 000;
else
downcounter=downcounter+1;
end endmodule
```








### RTL LOGIC UP COUNTER AND DOWN COUNTER  
![rtl6](https://user-images.githubusercontent.com/113975318/214319111-6deb2f75-033d-4f9c-8718-88f19ddf4692.png)
![image](https://user-images.githubusercontent.com/113975318/214319433-70807701-4f66-4132-bfd6-fcf91bd76576.png)











### TIMING DIGRAMS FOR COUNTER  
![tg6](https://user-images.githubusercontent.com/113975318/214319147-bf746975-dd05-4ab1-8abd-96d5e64f197c.png)
![image](https://user-images.githubusercontent.com/113975318/214319505-f80d37d2-5e35-4758-b155-7743002a07d5.png)






### TRUTH TABLE 
![tt6](https://user-images.githubusercontent.com/113975318/214319179-6ebf7a5f-4d06-45b6-8f15-f443f98a7037.png)

![image](https://user-images.githubusercontent.com/113975318/214319547-ddd0b39b-174e-45ef-8617-d2b761684a21.png)






### RESULTS 
Hence the Four bit Up counter and Down counter is implemented successfully and its functionality is validated.
