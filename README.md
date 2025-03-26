# annual-clock
Repository for CHRONOS Annual Clock code

Original code base tested successfully on February 19, 2025. First upload to GitHub of the original code base, improved version, and improved version with provision for debugging on an attached display on March 26, 2025.

The CHRONOS Annual Clock combines the mechanism of a traditional clock with a circular calendar, providing a new and different way of visualizing the year. 

The CHRONOS Annual Clock is an electronics and 3D Printing project that will be available on MakerWorld later this Spring.

The clock face is marked with the 12 months, signs of the Zodiac, and the seasons. Seasons are available in reverse for those in the Southern Hemisphere. Both an English language and an International version (with symbols) are available.

HARDWARE
- ESP32 Dev Kit C microcontroller (38 pins)
- ESP32 microcontroller breakout board (optional, but very useful)
- LM393 / H206 Slot-type Photo Interrupter Sensor module (LM393 is the microcontroller used, and H206 indicates the size of the gap)
- DS3231 AT24C32 Real Time Clock (RTC) Module
- 28BYJ-48 4-Phase Stepper Motor
- ULN2003 Motor Controller Board
- (For debug version only) SSD 1306 OLED Display 128 x 64 pixels

DESCRIPTION OF OPERATION

On startup, the ESP32 microcontroller will connect to your WiFi (using the credentials you have provided) and get the current date and time from the internet. 

Next, the homing procedure causes the clock’s hands, which are joined and parallel to each other, to rotate clockwise until the invisible hand interrupts the infrared beam projected across the gap of the photo interrupter sensor. The sensor marks the location of December 21. This will be the date of the winter equinox for much of the 21st Century, although it is dependent on location. 

Once the sensor is tripped, the ESP32 performs a calculation that moves the hand by the appropriate number of steps to reach today’s date and time. It will continue to update the hand’s position as time passes.

Improvements implemented since Feb. 19:

- Improved stepper motor handling
- Improved date handling
- Improved variable handling
- Improved failure handling
- Improved accuracy
