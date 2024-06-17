# 111_Days_Of_Verification
Dive in VLSI Verifications from Basics

# Index:

## Day 1 : Flip-Flop and Latches:
### [Functions of S-R Flip-Flop](#functions-of-s-r-flip-flop-1)
### [Functions of J-K Flip-Flop](#functions-of-j-k-flip-flop-1)
### [Differences between Flip-Flops and Latches](#differences-between-flip-flops-and-latches-1)
### [Why latches are faster than flip-flops](#why-latches-are-faster-than-flip-flops-1)
### [Applications of Flip-Flops](#applications-of-flip-flops)
### [Applications of Latches]

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

S-R Latch using NOR Gates:

![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/6fde781f-5403-4dad-95a5-095970879c50)

S'-R' Latch using NAND Gates:

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


**<ins>Applications of JK Flip-Flop:**

<ins>Counters::</ins> These are very essential components for the application of frequency dividers and event sequencers where there is a need of storing and propagating the count value. We can design binary synchronous and asynchronous counters using JK-flipflop.

<ins>Shift registers::</ins> For data storage and manipulation, serial-to-parallel or parallel-to-serial data conversion the shift registers are widely used. Registers can store and shift the binary data in a sequential manner. We can design it by JK-flipflops.

<ins>Memory Units::</ins> JK-flipflop itself act as a memory unit to store binary information. By making a sequential chain of JK-flipflops we can use it even as RAM.

**<ins>Advantages of JK Flip-Flop:**

<ins>Versatility::</ins> As discussed above, JK-flipflops can be used as a basic memory element or a primary building block of further complex memory design. It is very much adaptive as it can be operated in both synchronous and asynchronous modes.

<ins>Toggle Functionality::</ins> The application which are required to get output as its complement of input that also can be developed by JK-flipflops as when J=K=1 it triggers toggle state which gives output which is complement with it’s each clock pulse.

<ins>Error Detection and Correction::</ins> We can use a complex circuit built by JK-flipflops which can detect and correct information during data-transmission.

**<ins>Disadvantages of JK Flip-Flop:**

<ins>Complexity::</ins> Compared to other types of flipflops(D,T, SR), JK flipflop requires additional logic gates to implement which consumes extra memory resources and increases complexity to operate.

<ins>Propagation Delay::</ins> This is the major problem present in JK-FF. Propagation delay results a timing delay in certain application which are time-flow sensitive.

<ins>Race Problem::</ins> This issue arises when the clock input’s timing pulse isn’t given enough time to turn “Off” before the output Q’s state is altered.



### Differences between Flip-Flops and Latches


![image](https://github.com/sreemoyee-chatterjee9/111_Days_Of_Verification/assets/123591219/cf6a9373-f4c1-452e-bc10-188840f3e1fc)


### Why latches are faster than flip-flops

Both latches and flip-flops are used as memory elements in sequential circuits. The primary difference between a latch and a flip-flip is in their operations.

A latch is level-sensitive. It is transparent. Hence,its output changes as soon as the input changes. This makes latches faster in terms of setup time compared to flip-flops. In a latch, the output changes immediately when the input changes and remains latched until the latch is disabled.

On the other hand, a flip-flop is edge-triggered. its output changes only on a clock edge (rising or falling edge). This introduces an additional delay compared to latches because the input change must meet the setup time requirement before the clock edge to guarantee proper operation. This setup time requirement limits the maximum clock frequency at which a flip-flop can operate effectively.

Therefore, because latches are transparent and respond immediately to input changes, they are generally faster than flip-flops in terms of processing speed. 

### Applications of Flip-Flops

- Frequency dividers
- Counters :
  The term counter indicates a circuit that progressively shows the numbers. These counter circuits are implemented to display binary numbers in sequential order with the help of a clock pulse. Some common counters are counter 2 circuit, counter 4 circuit and even counter 7 circuit.
- Storage registers
- Shift registers :
  Shift registers are used to transfer data bits one by one to the next register. By temporarily storing data and then transmitting data when they receive clock impulse, they help to transfer data. This is essentially useful for rotate operations and series-parallel conversions.
- Data storage :
  Flip-Flips have the ability to store different states in a circuit making them the basic block. They are termed as storage registers and can store data in terms of ‘0’ and ‘1’. Therefore multiple flip flops can be used to store large data bits.
- Bounce elimination switch
- Latch
- Data transfer
- Memory
- Registers


### Applications of Latches

Generally, latches are used to keep the conditions of the bits to encode binary numbers. Latches are single bit storage elements which are widely used in computing as well as data storage. Latches are used in the circuits like power gating & clock as a storage device. D latches are applicable for asynchronous systems like input or output ports. Data latches are used in synchronous two-phase systems for reducing the transit count.

The applications of these basic digital elements are

- These circuits are known for storing the information in the form of bits. These are known as memory elements.
- The usage of pulse latches follows the same behavior of flip-flops but good enough to generate a quick response.
- In the two-phase synchronous systems to avoid the transit count, the data latches (D-Latches) are used.
- It is widely used to store the data and the codes for computations.
