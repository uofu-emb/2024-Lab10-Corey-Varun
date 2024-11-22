# Observations

## Default Register Values

**WAKE_EN** : 0x01

**SLEEP_EN** : 0x01

**ENABLE** : 0x00

***
***

### The following are the recorded power consumption measurements for various scenarios:

## Blinking LED using sleep_ms function

- **Input Voltage:** 5V  
- **Current Consumed:**
  - During LED off: **18mA**
  - During LED on: **20mA**
- **Power Consumption:**
  - During LED off: **0.09W**  
  - During LED on: **0.1W**


## Blinking LED using Free_RTOS thread

- **Input Voltage:** 5V  
- **Current Consumed:**
  - During LED off: **21.1mA**
  - During LED on: **23.3mA**
- **Power Consumption:**
  - During LED off: **0.1055W**  
  - During LED on: **0.1165W**

## Busy loop to get 100% CPU utilization.

- **Input Voltage:** 5V  
- **Current Consumed:** 21mA
- **Power Consumption:** 0.105W

## External Interupt

- **Input Voltage:** 5V  
- **Current Consumed:**
  - 1kHz: **18.1mA**
  - 10kHz: **18.2mA**
  - 100kHz: **19.2mA**
  - 1MHz: **20.5mA**
- **Power Consumption:**
  - 1kHz: **0.0905W**  
  - 10kHz: **0.091W**
  - 100kHz: **0.096W**
  - 1MHz: **0.1025W**

## Example Code - hello_sleep_alarm.c

- **Input Voltage:** 5V  
- **Current Consumed:**
  - Awake State: **17.95mA**
  - Sleep State: **1.1mA**
- **Power Consumption:**
  - Awake State: **0.08975W**  
  - Sleep State: **0.0055W**

## Example Code - hello_dormant_gpio.c

- **Input Voltage:** 5V  
- **Current Consumed:**
  - Awake State: **17.9mA**
  - Sleep State: **0.65mA**
- **Power Consumption:**
  - Awake State: **0.0895W**  
  - Sleep State: **0.00325W**