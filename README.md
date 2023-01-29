# CH32V307RCT6_breakout_hz

This is a simple breakout board for the CH32V307RCT6. This chip is cheap and contains high-speed USB peripheral, which is uncommon for MCUs. 

The intended use case is to receive data from the high-speed USB, and transfer that to SPI/UART/I2S at high data rate to drive DAC/ADC for lab automation / monitoring purpose. Hence, some of the SPI related pins have resistors for impedance matching / improve the signal integrity if used at high frequency.

In Jan 2023, this board is successfully used to drive a home built DAQ board (1 ADC and 1 DAC) which allows for its use as a digital PID circuit. To drive the SPI transactions with accurate timing, I used various timer channels to initiate DMA transfer, instead of using the SPI TX DMA. It could achieve a sampling rate of 400kSPs on MAX5719/AD5542/ADS8863. The hardware floating point support also makes PID calculation reasonably fast. (However there might be some compiler inefficiencies? Yet to be investigated). Although the final PID board would probably want to integrate all components (MCU + DAC/ADC + potential amplifier) in a single board, this breakout board was very useful for prototyping.

Also in Jan 2023, a basic test with SD card (using official SDIO example code) was sucessful. It seems the pull-up resistors helped and was indedd necessary.


This design is part of work of the BEC5 lab.
