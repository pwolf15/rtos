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