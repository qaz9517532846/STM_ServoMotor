# STM_ServoMotor
How to control a servo motor using NUCLEO-H743ZI2 board.

- Hardware:  NUCLEO-H743ZI2 board, servo motor(Tower Pro-MG 996R).

- Software: [STM32CubeMX](https://www.st.com/en/development-tools/stm32cubemx.html) and [Keil uVision5](https://www2.keil.com/mdk5/uvision/).

------

### STM32 Setting Parameter

- System Clock = 32 MHz.

- Prescaler = 640 - 1.

- Counter Period = 1000 - 1.

------

### Circuit

![image](https://github.com/qaz9517532846/STM_ServoMotor/blob/main/circuit/STM_ServoMotor.png)

------

### PWM control

- Servo Motor Frequency = 50 Hz.

- Pulse Width(0 to 180 degree):
  - 1ms => -90 degree
  - 1.5ms => 0 degree
  - 2ms => 90 degree

- Calculate worck cycle:
  - 1ms => 1 / 20 * 100% = 5%
  - 1.5ms => 1.5 / 20 * 100% = 7.5%
  - 2ms => 2 / 20 * 100% = 10%

- Calculate CCR:
  - 1ms =>  5% * 1000 = 50
  - 1.5ms => 7.5% * 1000 = 75
  - 2ms => 10% * 1000 = 100

------

### Result

After testing it from 1 ms to 2ms, I found that the servo was not rotating the full 180 degrees as it should So I decided to take it a little further and tested it from 0.5 ms to 2.5 ms and It performed well. So the code below is for 0.5 to 2.5 ms, However I commented out the section for 1 to 2 ms.

------
### Reference

[1]. Servo motor with STM32. https://controllerstech.com/servo-motor-with-stm32/

[2]. STM32H743ZI MCU. https://www.st.com/en/evaluation-tools/nucleo-h743zi.html

------

This repository is for your reference only. copying, patent application, academic journals are strictly prohibited.

Copyright © 2021 ZM Robotics Software Laboratory.
