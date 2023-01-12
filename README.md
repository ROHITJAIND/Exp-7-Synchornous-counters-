Developed By: ROHIT JAIN D  
Reference No: 22005894  

# AIM:  
To implement 4 bit up and down counters and validate  functionality.
# HARDWARE REQUIRED:  
- PC
- Cyclone II
- USB flasher
# SOFTWARE REQUIRED:   
- Quartus prime
# THEORY 

# UP COUNTER 
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



# DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
# Procedure
1.Create a new project in QuartusII software.<br>
2.Name the project as uc for upcounter and dc for down counter.<br>
3.Create a new verilog hdl file in the project file.<br>
4.Name the module as dc and uc for down counter and up counter.<br>
5.Within the module declare input and output variables.<br>
6.Create a loop using if-else with condition parameter as reset value.<br>
7.End the loop.<br>
8.End the module.<br>

# PROGRAM 
Program for flipflops  and verify its truth table in quartus using Verilog programming.
- UP COUNTER:  
```
module UPCOUNTER(input clk,input reset,output[0:3]counter);
reg[0:3] counter_up;
always@(posedge clk or posedge reset)
begin
if(reset)
counter_up<=4'd0;
else
counter_up<=counter_up+4'd1;
end
assign counter=counter_up;
endmodule
```
- DOWN COUNTER:
```
module DOWNCOUNTER(input clk,input reset,output[0:3]counter);
reg[0:3] counter_down;
always@(posedge clk or posedge reset)
begin
if(reset)
counter_down<=4'd0;
else
counter_down<=counter_down-4'd1;
end
assign counter=counter_down;
endmodule
```
# RTL LOGIC UP COUNTER AND DOWN COUNTER  
- UP COUNTER:

![Screenshot_20230112_050143](https://user-images.githubusercontent.com/118707073/212065504-256cd8a7-4b38-424d-9317-5d3c64fcb62a.png)


- DOWN COUNTER:

![Screenshot_20230112_051347](https://user-images.githubusercontent.com/118707073/212065517-0a5a8355-abf8-47f6-b818-f56cb2552c3c.png)


# TIMING DIGRAMS FOR COUNTER  
- UP COUNTER:

![Screenshot_20230112_050800](https://user-images.githubusercontent.com/118707073/212065548-9f3881e0-deab-4dcf-a5ee-b8a79eba35ed.png)


- DOWN COUNTER:

![Screenshot_20230112_055428](https://user-images.githubusercontent.com/118707073/212065816-1c3e71ac-f76f-40bd-b6a9-c82f2cb470c3.png)

# TRUTH TABLE 
- UP COUNTER:

![WhatsApp Image 2023-01-12 at 17 51 06](https://user-images.githubusercontent.com/118707073/212065918-5280d0bb-49c7-4c7a-b6ea-0147e44caebe.jpg)

- DOWN COUNTER:

![WhatsApp Image 2023-01-12 at 17 51 07](https://user-images.githubusercontent.com/118707073/212065954-2161f0de-54b0-47f1-97ab-3133ab7b9432.jpg)


# RESULTS :
Thus Synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
