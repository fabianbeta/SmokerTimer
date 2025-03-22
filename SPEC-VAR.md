Raspberry Pi Pico PWM Controller, using 2× 10,000 ohm potentiometers
GPIO 26 (ADC0): Pot 1 for off-time control (0-5000ms)
GPIO 27 (ADC1): Pot 2 for pulse width control (30-200ms)
GPIO 16: Output pin that shorts to 5V line to trigger smoke machine (CON)
Power: 5V into VSYS pin (Pin 39)
Onboard RGB LED for status indication

LED Status Indicators (Using Pico's onboard RGB LED)
Startup sequence: Green LED blinks 5× (100ms on, 200ms apart)
Normal operation: Blue LED when system is active but output is OFF
During pulse: Red LED when output pulse is ON
System must complete startup sequence before enabling output

Software and Dev: MicroPython implementation in Thonny IDE
Input handling:
Average 15 potentiometer samples over 75ms period
Apply software debounce to potentiometer readings
Error handling with fallback to previous valid values

Memory management: Run garbage collection every 45 minutes
Fallback: If pot readings are invalid, stop output and continuously blink onboard blue LED for 100ms and 500ms apart
Watchdog timer implementation for system reliability 
Beginner-friendly code structure with clear module separation and comprehensive comments

Implementation Guidelines

Define configuration constants at the top for easy tuning
Structure code in logical modules with clear headers
Include detailed error handling for ADC reading failures
Implement proper RGB LED control for status indication
Focus on reliability and readability over optimization




