# chronos-annual-clock
Repository for CHRONOS Annual Clock code

Original code base tested successfully on February 19, 2025. First upload to GitHub of the original code base, improved version, and improved version with provision for debugging on March 30, 2025.

The CHRONOS Annual Clock combines the mechanism of a traditional clock with a circular calendar, providing a new and different way of visualizing the year. 

The CHRONOS Annual Clock is an electronics and 3D Printing project that will be available on MakerWorld (makerworld.com) later this Spring.

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


POSIX TX time zone strings for select locales:
Alaska: AKST+9AKDT,M3.2.0/2,M11.1.0/2
Argentina: ART3
Australia, Central: ACST-9:30ACDT,M10.1.0/2,M4.1.0/3
Australia, Eastern: AEST-10AEDT,M10.1.0/2,M4.1.0/3
Australia, Western: AWST-8
Belgium: CET-1CEST,M3.5.0/2,M10.5.0/3
Brazil: BRT3
China: CST-8
Finland: EET-2EEST,M3.5.0/3,M10.5.0/4
France: CET-1CEST,M3.5.0/2,M10.5.0/3
Germany: CET-1CEST,M3.5.0/2,M10.5.0/3
Greece: EET-2EEST,M3.5.0/3,M10.5.0/4
Hawaii: HST10
Iceland: GMT0
India: IST-5:30
Indonesia (Jakarta): WIB-7
Ireland:GMT0IST,M3.5.0/1,M10.5.0/2
Italy: CET-1CEST,M3.5.0/2,M10.5.0/3
Japan: JST-9
Mexico: CST6CDT,M4.1.0/0,M10.5.0/0
NA Central (Chicago, Winnipeg): CST6CDT,M3.2.0/2,M11.1.0/2
NA Eastern (New York, Montreal): EST5EDT,M3.2.0/2,M11.1.0/2
NA Mountain (Denver, Calgary): MST7MDT,M3.2.0/2,M11.1.0/2
NA Mountain no DST (Phoenix): MST7
NA Pacific (Los Angeles, Vancouver): PST8PDT,M3.2.0/2,M11.1.0/2
Netherlands: CET-1CEST,M3.5.0/2,M10.5.0/3
New Zealand: NZST-12NZDT,M9.5.0/2,M4.1.0/3
Newfoundland: NST3:30NDT,M3.2.0/2,M11.1.0/2
Pakistan: PKT-5
Portugal: WET0WEST,M3.5.0/1,M10.5.0/2
Puerto Rico: AST4
Singapore: SGT-8
South Korea: KST-9
Spain: CET-1CEST,M3.5.0/2,M10.5.0/3
Taiwan: CST-8
Ukraine: EET-2EEST,M3.5.0/3,M10.5.0/4
United Kingdom: GMT0BST,M3.5.0/1,M10.5.0/2


