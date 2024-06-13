# 111_Days_Of_Verification
Dive in VLSI Verifications from Basics

# Index:

## Day 1 : Flip-Flop and Latches:
### [Functions of S-R Flip-Flop](#functions-of-s\-r-flip\-flop)
### [Functions of J-K Flip-Flop](#functions-of-J\-K-flip\-flop-1)

### Functions of S-R Flip-Flop

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



### Functions of J-K Flip-Flop

![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/5119f66a-b274-4314-b01d-35a19821080b)

To overcome following switching problems of S-R Flip-Flops, J-K Flip-Flop was developed.

1. For S-R Nand Gate Flip-Flop, Set = 0 and Reset = 0 condition (S = R = 0) must always be avoided to omit the race-around condition.
2. If Set or Reset change state while the enable (EN) input is high, the correct latching action may not occur.

The JK flip flop is a **gated SR flip-flop** with the addition of a clock input circuitry that prevents the illegal or invalid output condition that can occur when both inputs S and R are equal to logic level “1”. Due to this additional clocked input, a JK flip-flop has four possible input combinations, “logic 1”, “logic 0”, “no change” and “toggle”. 

If both the J and K inputs are HIGH at logic “1” (J = K = 1), when the clock input goes HIGH, the circuit will “toggle” as its outputs switch and change state complementing each other. This results in the JK flip-flop acting more like a T-type toggle flip-flop when both terminals are “HIGH”. However, as the outputs are fed back to the inputs, this can cause the output at Q to oscillate between SET and RESET continuously after being complemented once.

While this JK flip-flop circuit is an improvement on the clocked SR flip-flop it also suffers from timing problems called “race” if the output Q changes state before the timing pulse of the clock input has time to go “OFF”. To avoid this the timing pulse period (T) must be kept as short as possible (high frequency). As this is sometimes not possible with basic JK’s built using basic NAND or NOR gates, far more advanced master-slave (edge-triggered) flip-flops were developed which are more stable.

![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/c7543a12-0990-41cb-987c-09ac57ff671a)

**<ins>Operation Modes of JK Flip Flop:**

Apart from its basic functionality, there are two essential operating modes in JK Flip Flop: edge-triggered and level-triggered.

**Edge-Triggered:** In this mode, flip flop responds to a signal transition occurring at a clock pulse. It is commonly used in synchronous systems, where the output changes only when the clock signal changes from low to high or high to low. The edge-triggered JK Flip Flop ensures stable output and prevents glitches caused by rapid changes in input values.

**Level-Triggered:** Unlike the edge-triggered mode, the level-triggered JK Flip Flop responds to the input values continuously as long as the clock signal is held at a specific level (high or low). This mode is mainly used in asynchronous systems or applications where the input changes are directly reflected in the output.


Applications of JK Flip-Flop
We can simply implement a JK-flipflop using NAND gates. In that case two NAND gates need to be connected together and the output of that will be feed to the input which will create a stable state-holding circuit. The resulting circuit will be the NAND gate. So, by following this mechanism we can develop and use JK-flipflop for various application which are listed below.

Counters: These are very essential components for the application of frequency dividers and event sequencers where there is a need of storing and propagating the count value. We can design binary synchronous and asynchronous counters using JK-flipflop.
Shift registers: For data storage and manipulation, serial-to-parallel or parallel-to-serial data conversion the shift registers are widely used. Registers can store and shift the binary data in a sequential manner. We can design it by JK-flipflops.
Memory Units: JK-flipflop itself act as a memory unit to store binary information. By making a sequential chain of JK-flipflops we can use it even as RAM.
Advantages of JK Flip-Flop
Versatility: As discussed above, JK-flipflops can be used as a basic memory element or a primary building block of further complex memory design. It is very much adaptive as it can be operated in both synchronous and asynchronous modes.
Toggle Functionality: The application which are required to get output as its complement of input that also can be developed by JK-flipflops as when J=K=1 it triggers toggle state which gives output which is complement with it’s each clock pulse.
Error Detection and Correction: We can use a complex circuit built by JK-flipflops which can detect and correct information during data-transmission.
Disadvantages of JK Flip-Flop
Complexity: Compared to other types of flipflops(D,T, SR), JK flipflop requires additional logic gates to implement which consumes extra memory resources and increases complexity to operate.
Propagation Delay: This is the major problem present in JK-FF. Propagation delay results a timing delay in certain application which are time-flow sensitive.
Race Problem: This issue arises when the clock input’s timing pulse isn’t given enough time to turn “Off” before the output Q’s state is altered.
