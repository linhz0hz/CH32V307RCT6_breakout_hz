# CH32V307RCT6_breakout_hz

This is a simple breakout board for the CH32V307RCT6. This chip is cheap and contains high-speed USB peripheral, which is uncommon for MCUs. 

The intended use case is to receive data from the high-speed USB, and transfer that to SPI/UART/I2S at high data rate to drive DAC/ADC for lab automation / monitoring purpose. Hence, some of the SPI related pins have resistors for impedance matching / improve the signal integrity if used at high frequency.

This design is part of work of the BEC5 lab.
