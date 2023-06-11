### Ex. No. 6
#### Date: 19.5.23
# Implementation of 4 bit synchronous counters using Verilog HDL
## Aim:
To design and implement the following synchronous counters using Verilog HDL.
1.	UP counter
2.	DOWN counter
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
A Synchronous counter is the counter in which the clock input with all the flip-flops uses the same source and produces the output at the same time.
## UP Counter
### State table
![image](https://github.com/rvinifa/Counter/assets/133735746/ede78598-89fd-4aeb-9d82-329e45d05f2a)

### K-map Simplification

   ![image](https://github.com/rvinifa/Counter/assets/133735746/21554263-611b-44a2-8f78-7b2220ef5a05)
   
### Logic Diagram
![image](https://github.com/rvinifa/Counter/assets/133735746/2ab715d3-f6d5-4cf6-8fda-8fa666518c0b)



## DOWN Counter
### State Table
 ![image](https://github.com/rvinifa/Counter/assets/133735746/5be9585c-11aa-47c3-beaf-0dca916750f2)

### K-map simplification
 ![image](https://github.com/rvinifa/Counter/assets/133735746/dde7bc60-3a4f-4fb7-811d-f420cb74bdef)

### Logic Diagram
 ![image](https://github.com/rvinifa/Counter/assets/133735746/64e2d7b7-1646-4ca7-bc6c-c7c10881223c)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
~~~
1.
module exp6(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always@(posedge clk)
begin
  q4=(q1&q2&q3)^q4;
  q3=(q1&q2)^q3;
  q2=q1^q2;
  q1=1^q1;
end
endmodule
~~~
~~~
2.
module exp6b(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always @(posedge clk)
begin
q4=((~q3)&(~q2)&(~q1))^q4;
q3=((~q2)&(~q1))^q3;
q2=(~q1)^q2;
q1=1^q1;
end
endmodule
~~~


## RTL Schematic:
![exp 6 a (2)](https://github.com/PresillaMary/Counter/assets/129305503/a48ecc33-f7fd-4eac-b110-df6222b36c4e)
![6b](https://github.com/PresillaMary/Counter/assets/129305503/8b3d1d25-2e1a-429e-a5d7-f07ee9d55f25)




## Timing Diagram:
![exp 6a](https://github.com/PresillaMary/Counter/assets/129305503/fecc738c-5092-4b2c-9fb3-e9ed9801afd9)

![6b (2)](https://github.com/PresillaMary/Counter/assets/129305503/2e794d4e-765c-456e-9c95-54bfa624f04f)


## Result:
Thus the Synchronous UP and DOWN counters using T flipflops are implemented and the state tables are verified.

