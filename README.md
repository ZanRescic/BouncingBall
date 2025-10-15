# Bouncing Ball

A simple touchscreen game demo for the **STM32H750B-DK** development board.  
The project demonstrates basic game logic, LCD graphics rendering, and touchscreen input using STM32 HAL and BSP libraries in **STM32CubeIDE**.

## Overview

The game features a ball that continuously falls under gravity.  
The player taps the touchscreen to make the ball bounce — each successful bounce increases the score.  
When the ball falls off the bottom of the screen, the game ends and the final score and elapsed time are displayed.

This project serves as a lightweight example of using the **LCD display** and **capacitive touchscreen** on the STM32H750B-DK board.

## Hardware Requirements

- STM32H750B-DK development board  
- USB connection for programming and power  
- On-board LCD and touchscreen (integrated on the DK board)


## Software Requirements

- [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html)  
- STM32H7 HAL and BSP drivers (included with CubeIDE board support package)

## Setup and Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/ZanRescic/STM32H750B-DK_BouncingBall.git
2. Open the project in STM32CubeIDE.

3. Build and flash the firmware to the STM32H750B-DK board.

4. After flashing, the game will start automatically on the LCD screen.
