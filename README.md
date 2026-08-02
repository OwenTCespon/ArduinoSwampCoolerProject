# Arduino Swamp Cooler Controller

## Overview

Working as a team of four, we designed and programmed an automated swamp cooler controller using an Arduino Mega. The system continuously monitors environmental conditions and water level, automatically controls a fan, allows vent adjustment, and provides status feedback through an LCD display and LEDs.

Rather than relying solely on Arduino's built-in functions, much of the project was implemented using **direct AVR register manipulation**, providing greater control over the microcontroller hardware and reinforcing embedded systems concepts.

---

## Features

* Automatic temperature and humidity monitoring
* Water level detection with low-water protection
* Four-state finite state machine:

  * Disabled
  * Idle
  * Running
  * Error
* Automatic fan control based on temperature threshold
* Manual vent adjustment using a stepper motor
* LCD display showing:

  * Temperature
  * Humidity
  * Error messages
* Real-Time Clock (RTC) timestamps over serial communication
* LED indicators for each operating state
* Interrupt-driven start button
* ADC-based analog water level sensing

---

## Hardware Used

* Arduino Mega 2560
* DHT11 Temperature & Humidity Sensor
* Water Level Sensor
* Stepper Motor
* DC Fan
* DS1307 Real-Time Clock (RTC)
* 16x2 LCD Display
* Push Buttons
* LEDs

---

## Software Concepts

This project demonstrates several embedded systems concepts, including:

* Direct register programming
* ADC configuration and analog sensor reading
* USART serial communication
* Interrupts
* State machine design
* Stepper motor control
* Real-time monitoring
* Sensor integration
* Embedded hardware interfacing

---

## System Operation

The controller operates as a finite state machine.

### Disabled

* System is off
* Fan is disabled
* Yellow LED indicates the disabled state
* Vent can still be manually adjusted

### Idle

* Continuously monitors temperature and humidity
* Displays sensor data on the LCD
* Waits for temperature to exceed the configured threshold

### Running

* Fan is enabled
* Blue LED indicates the system is actively cooling
* Continues monitoring environmental conditions
* Returns to Idle once the temperature falls below the threshold

### Error

* Triggered when the water level falls below the minimum threshold
* Fan is disabled to protect the system
* LCD displays an error message
* Red LED indicates the fault
* System waits for reset after water is replenished

---

## Team Members

* Owen Cespon
* Cal Peters
* Brendan McPartlin
* Scott McKenzie

---

## Skills Demonstrated

* Embedded C/C++
* Arduino development
* AVR register manipulation
* Hardware debugging
* Finite state machine implementation
* Sensor integration
* Team software development
* Embedded systems design

---

## Future Improvements

Potential enhancements include:

* Variable-speed fan control using PWM
* Wireless monitoring via Bluetooth or Wi-Fi
* Mobile application for remote monitoring
* SD card data logging
* Automatic vent positioning based on temperature
* Improved power management
* Additional environmental sensors

---
