# Project Name: STM32 and Python Data Acquisition System

## Overview

This project is a data acquisition system that interfaces an STM32 microcontroller with various sensors and a PC application built using Python. The microcontroller, programmed in C, is responsible for collecting real-time data from multiple sensors and transmitting it via a communication interface to a Python-based application, where the data is processed, visualized, and stored. The schematic diagrams and PCB designs for the hardware implementation are included as part of this repository.

## Features

- **Sensor Data Collection**: STM32 microcontroller collects data from speed, torque, current, and battery sensors.
- **Real-time Data Processing**: Python script to receive data, process, and generate meaningful insights.
- **Custom PCB Design**: The hardware interface consists of a custom PCB, designed using EasyEDA, which hosts the STM32 and sensor connections.
- **Communication**: Serial communication between STM32 and PC.
- **Visual Interface**: Python script includes visualization tools to plot and analyze the incoming sensor data.

## Hardware Components

### STM32 Microcontroller
The project utilizes the STM32F103C8T6 microcontroller, also known as the "Blue Pill." The STM32 is the core component responsible for interfacing with all the sensors and sending data to the PC application.

### Sensors
- **Speed Sensor**: The speed sensor is connected through an analog input pin, and the data is filtered with capacitors for noise reduction.
- **Torque Sensor**: The torque data is acquired in real-time, filtered, and sent to the microcontroller's ADC for processing.
- **Current Sensor**: Current is measured using a shunt and resistor divider network, further conditioned before feeding it to the microcontroller.
- **Battery Sensor**: Battery voltage levels are also monitored and conditioned appropriately.

### PCB Design
The schematic and PCB design are made in EasyEDA, which includes the STM32 microcontroller, sensor input circuits, and LM2596 buck converter for stable power regulation. The PCB layout ensures minimal noise interference and ease of component placement.

- **Files Included**: The EasyEDA schematic and PCB layout files are available in the repository.

### Power Supply
The board uses an LM2596 DC-DC buck converter to convert 12V input to 5V, providing power to the entire system, ensuring a stable supply.

## Software Components

### STM32 Code (C Language)
The microcontroller code is written in C and is responsible for:

1. **Analog Data Acquisition**: Reading ADC values from speed, torque, current, and battery sensors.
2. **Data Transmission**: Sending data to the Python application through UART communication.
3. **Real-Time Processing**: Basic calculations on the microcontroller before transmitting the data.

#### Compilation and Flashing
- The code is compiled using STM32CubeIDE, and flashing is done using an ST-Link V2.
- The `main.c` file provides details of all the functions used for data acquisition, UART communication, and control logic.

### Python Application
The Python code (`main.py`) is used to interact with the STM32 microcontroller.

- **Communication**: The `pyserial` library is used to establish serial communication with the STM32, receiving the data sent from the microcontroller.
- **Data Processing**: The Python application processes raw sensor data, applying filters and making calculations to determine various parameters.
- **Data Visualization**: Matplotlib is used to visualize the incoming data in real-time, allowing for easy monitoring and analysis of speed, torque, current, and battery voltage.

#### Dependencies
- Python 3.x
- pyserial: To handle serial communication between STM32 and PC.
- matplotlib: To plot sensor data in real-time for better visualization.

#### Running the Python Script
- Make sure that the STM32 board is connected to the PC.
- Run the script: `python main.py`

The script will automatically start receiving data and display real-time plots for the different sensor values.

## Project Setup

1. **Hardware Setup**
   - Connect the sensors as shown in the provided schematics.
   - Power the board with a 12V power supply, which will be regulated by the LM2596 buck converter.

2. **STM32 Programming**
   - Flash the `main.c` program onto the STM32 microcontroller using STM32CubeIDE and ST-Link.

3. **Python Script Setup**
   - Connect the STM32 board to the PC via a USB-UART bridge.
   - Run the Python script (`main.py`) to initiate data collection and visualization.

## Schematics and PCB Design
The detailed schematic and PCB layout are included in the repository (`schematic_1.jpeg` and `schematic_2.jpeg`).

### Schematic Highlights
- **Analog Signal Conditioning**: Filtering capacitors and resistors are used to ensure accurate ADC measurements.
- **UART Communication**: Connects the STM32 microcontroller to the PC for serial data transfer.

### PCB Highlights
- **Compact Design**: A small form-factor PCB designed with a proper ground plane to minimize noise.
- **Power Circuit**: Integrated LM2596 buck converter for a reliable 5V power supply.

## Usage and Applications
This system can be used in real-time monitoring and control applications where parameters like speed, torque, current, and battery levels are crucial. It is suitable for embedded systems courses, IoT-based projects, or data acquisition systems.

## Future Improvements
- Add Wi-Fi/Bluetooth communication to eliminate the need for USB-UART cables.
- Extend the Python application to support data logging and export to Excel/CSV.
- Implement machine learning models to predict sensor failures or anomalies.

## License
This project is licensed under the MIT License. Feel free to use, modify, and distribute as per the license terms.

## Contributions
Contributions are welcome! Feel free to open issues or submit pull requests for improvements and bug fixes.

## Contact
For any questions or inquiries, please feel free to reach out dev.alikaganmart@gmail.com .

