What is a real-time operating system (RTOS)?
What is a microcontroller unit?
What is real-time?
When should an RTOS be used?

A RTOS is any system that has a deterministic response to a event.
If a system is considered to fail when it doesn't meet a timing requirement, it must be real-time.
RT requirements can vary widely.

What is jitter?
What is a super loop?
What is polling and when is it used?
What are interrupts and interrupt service routines?
What is a nested vector interrupt controller?
What are latency and jitter int he context of ISRs?
What is interrupt tail chaining?
How to minimize instructions in ISR?
What is a direct memory access controller?
When is an RTOS needed?

What is an RTOS task?
What is a preemptive RTOS?
How to conceptualize tasks vs. super loop?
Round-robin scheduling
Preemptive scheduling
What is a tisk-less scheduler?
What is task starvation?

What are the pros and cons of RTOS task vs super loops?

Task Signaling and Communication Mechanisms

What is FIFO?
What is a queue?
What is a semaphore? Greek origin?
What are binary vs. counting semaphores?
How does waiting for a semaphore vary in an RTOS vs. most other semaphore implementations?
What wakes up a task to give it a semaphore?
Why doesn't a task need to give back a binary semaphore?
What is a mutex?
What is the difference between a binary semaphore and a mutex?
What is priority inversion?
What is priority inheritance?

Core considerations when choosing an MCU
* Will it fit?
* Can it run all of my code?
* How much does it cost?
* Is it readily available?
Quad flat pack
Quad no lead
Ball-grid arrays

ROM: read-only memory => start with largest for development, determine optimal for scaling up
RAM: random-access memory => each RTOS task has own stack
BOM: bill-of-materials
Tradeoffs of external RAM
CPU clock rate
Interrupt processing: NVIC, EXTI
Price
Availability
Hardware peripherials
Connectivity: RMII, PHY, Ehenret, 802.11, 802.15.1, 802.15.4
Memory protection units (MPUs)
Hardware FPUs
DSP functions
DMA channels
I2C, SPI, USART
USARTs, CAN, LIN
Hardware crypto engines
Timing hardware: QEIs
SEGGER J-LINK
SEGGER Ozone
SEGGER SystemView

To get an RTOS application up and running
1. Initialize the MCU hardware.
2. Define your functions.
3. Map functions to RTOS tasks.
4. Start the scheduler.

How do you create a task using FreeRTOS APIs?
How do you delete a task?
Why is it important to check the return value of the create?
When is task deletion desired?
What is a TCB?

Troubleshoot
- Cannot open JLINK
=> Install JLINK first, then CUBE IDE due to issues with udev

Static vs. dynamic memory allocation vs. memory-protected task creation
xTaskCreate vs. xTaskCreateStatic
Heap implementations
Possible task states
Task starvation
Optimizing to reduce CPU time
1. polling => ISRS and DMA

Optimizing to increase performance
DMA and interrupts

Optimizing to minimize power consumption

Troubleshooting startup
- task creation failed?
- scheduler returns unexpectedly?

Protecting and Synchronizing Data Using Tasks
Tasks are meant to be programmed so that they run in parallel. No assumptions can be made where tasks are in their execution with respect to one another, unless they are explicitly synchronized.
Semaphores are one means of synchronization.
How is tick delay correlated to time?
Polling vs. semaphore (CPU utilization and task priority importance)
Does an RTOS guarantee the successful timeliness of an operation?
What are some use cases for counting semaphorees?
Try an example where you have at max 5 TCP connections at once.
https://www.youtube.com/watch?v=imVEMjjni-M

Should mutexes be used to protect a shared resource?

How do you avoid mutex acquisition failure?
What is a critical section?
What are software timers and why use them?
Why use hardware vs. software timers?
What is the timer service?
What is a oneshot vs. repeat timer?
What are use cases for timers?
What are the important considerations for the timer?
What are the limitations of the timer?

Intertask communications
How can data be passed between tasks?
How are queues created?
What are the pros and cons of using pass by reference vs. pass by value with queues?
What does a colon mean inside a declaration e.g.

``` c++
typedef struct
{
    uint32_t redLEDState : 1;
    uint32_t blueLEDState : 1;
    uint32_t greenLEDState : 1;
    uint32_t msDelayTime;
    char message[MAX_MSG_LEN];
} LedStates_t;
```

What are gotchas when passing by reference?
What are direct task notifications and why use them?
Tasks, queues, semaphores, and mutexes are the building blocks of RTOS applications.

UART: universal asynchronous receiver/trasnmitter
Direct memory access (DMA)
FreeRTOS stream buffers
What is UART?
How do you create a polled UART driver?
What is the difference between tasks and ISRs?
What are ISR-based drivers?
What are DMA based drivers?
WHat is STM HAL?

Objective: how to implement a UART driver

UART hardware takes bytes of data and transmits them over a wirte by moduling the voltage of a signal line at a predetermined rate.
Is a clock line required for UART?
USART: universal synchrnous/asynchronous receiver transmitter
USART can be either synchronous or asynchrounous (no clock signal)
UART foundation of RS232, RS422, RS485, Modbus, etc. Also, can be used for multi-processor communication and WiFi and Bluetooth transciever

What needs to be properly configured for UART to transmit?
- buad rate
- parity settings
- flow control
- stop bits

Setting up UART4
- configure GPIO lines

What is an interrupt status register?
What are the pros and cons of using a polled driver?
What are the similarities/differences between tasks and ISRs?
How do you program an ISR?
Can we use FreeRTOS APIs from ISRs?
How does the IRQHandler map a function name to an address in the vector table?
What does vectoring a program counter mean?
Is there a difference between a ring buffer and a circular buffer?
Why use a queue-based vs. bufffer-based ISR implementation?

What is a peripheral?