# STM32F407 ADC + PWM LED Dimmer
https://github.com/user-attachments/assets/457d1165-3eb9-42ff-a3ee-b941a908d894

Reads a potentiometer through ADC1 (PA1) and controls the brightness of the onboard green LED (PD12) using PWM from TIM4 Channel 1.

## Behavior

| Potentiometer Position | LED Brightness |
|------------------------|----------------|
| Fully left | Off (0% duty) |
| Middle | Half (50% duty) |
| Fully right | Full (100% duty) |

The ADC value (0–4095) is written directly to the PWM compare register, so brightness follows the potentiometer smoothly.

## Hardware

- STM32F407G-DISC1 Discovery board
- Potentiometer (wiper on PA1, ends on 3.3V and GND)

## Timing

- Timer clock: 16 MHz / (15+1) = 1 MHz
- PWM frequency: 1 MHz / (4095+1) = 244 Hz
- ADC sampling: 50 Hz (20 ms delay)

## Project structure

- `Core/Src/main.c` — application logic
- `Core/Inc/main.h` — header
- `stm32-adc-pwm-led-dimmer.ioc` — CubeMX configuration

## Build

1. Open the `.ioc` file in STM32CubeIDE.
2. Project → Build All.
3. Run → Debug.

## Tools

- STM32CubeIDE
- STM32CubeMX
- STM32 HAL library

## Author

Ali Bouzaienne
