# 111_Days_Of_Verification
Dive in VLSI Verifications from Basics

Index:

##Flip-Flop and Latches:
### Functions of S-R Flip-Flop


### Functions of S-R Flip-Flop:

![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/420f6657-2c6e-465d-ae1f-ce1bf309bc95)

**S = Set Input;**

**R = Reset Input;**

CASE 1. : S = 0; R = 0; Clock is toggling.

          Gate1 = 0, Gate2 = 0, Gate3 = (0+Q')'= Q, Gate4 = (0+Q)' = Q’.

          This is a hold state.

Case 2: S = 0, R = 1; Clock is toggling.

          Gate1 = 1, Gate2 = 0, Gate3 = (1+Q')' = 0, Gate4 = (0+0)' = 1.
          
Case 3: S=1, R=0; Clock is toggling.

          Gate1 = 0, Gate2 = 1, Gate3 = (0+Q')' = 1, Gate4 = (1+Q)' = 0.

Case 4: S=1, R=1; Clock is toggling.

          Gate1 = 1, Gate2 = 1, Gate4 = 0, Gate3 = 0.
          
          This is an invalid state. When both S and R are set to high as S=1 and R= 1, then the indeterminate state occurs.

Truth Table of S-R Flip Flop : 

![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/e64e0db1-b30c-452e-8978-48bcbcf0aba4)

S-R Flip Flop using NOR Gates:

![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/6fde781f-5403-4dad-95a5-095970879c50)

S'-R' Flip Flop using NAND Gates:

![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/b5c6eb7c-5ffa-4ee2-a58b-0b884597b10e)

Note : The dominating input of NAND gate is 0 i.e., if any of its input is Logic ‘0’, the output is Logic ‘1’, irrespective of the other input. The output is 0, only if all the inputs are 1.

![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/e487a413-bcdb-4651-a41a-16b08b40bc34)

**Advantages :-**

There are several advantages to using an SR flip-flop. Some of them are listed below: 

<ins>Simplicity:</ins> The SR flip-flop is a simple and easy-to-understand circuit.

<ins>Speed:</ins> The SR flip-flop is relatively fast, which makes it suitable for use in high-speed digital systems.

<ins>Low power consumption:</ins> The SR flip-flop consumes very little power, which makes it suitable for use in battery-powered devices.

<ins>Bi-stable operation:</ins> The SR flip-flop can be set and reset, making it a bi-stable circuit that can hold a state indefinitely until it is changed by an input signal.

**Limitations :-**

Apart from several advantages, there are some limitations associated with SR flip-flops. Some of them are listed below: 

<ins>Race condition:</ins> The SR flip-flop is susceptible to race conditions, which occur when the output state changes unpredictably due to variations in the timing of input signals.

<ins>Invalid states:</ins> If both the set and reset inputs are activated at the same time, the SR flip-flop can enter an invalid state where both outputs are high or both are low. This can lead to unpredictable behavior in digital systems.

<ins>Limited scalability:</ins> The SR flip-flop can be difficult to scale up to more complex digital systems, as it can lead to increased complexity and the potential for errors.

**Applications :-**

Some of the applications of SR flip-flop in real-world includes: 

<ins>Control systems:</ins> The SR flip-flop is used in control systems to synchronize signals and coordinate the operation of other components in the system. For example, in a traffic light control system.

<ins>Memory storage:</ins> The SR flip-flop is used in memory storage devices such as registers, which are used to store data temporarily. Registers are used in a wide range of applications, including microprocessors, digital signal processors, and other digital circuits.

<ins>Digital counters:</ins> The SR flip-flop can be used in digital counters to count up or down based on an input signal. For example, a timer circuit.

<ins>Data synchronization:</ins> The SR flip-flop can be used to synchronize data signals between two digital circuits, ensuring that they are operating on the same clock cycle. This is useful in communication systems where data needs to be transmitted and received at specific times.

<ins>Oscillators:</ins> The SR flip-flop can be used in conjunction with other components to create simple oscillators that generate a periodic signal. This is useful in applications such as clock circuits and audio signal generators.
