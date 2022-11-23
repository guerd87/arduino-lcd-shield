# arduino-lcd-shield
Open source LCD shield suitable for Arduino boards

http://home.johnhobson.ws/arduinolcd.html

DIY Arduino LCD Shield

After playing around with my Arduino I quickly realised every project I had made required an LCD display. I set about making a LCD Shield to go on top of a standard Arduino. The circuit uses a 16x2 LCD with the common 44780 chipset. To save on pins this is then run through a 4094 8-Bit Shift Register. Running the LCD in 4-bit mode it can be hooked up with 6 wires. Using a shift register allows it to be used with only 3 ports from the Arduino.

After I designed the circuit in Eagle I etched a proto board up. I used some Arduino stackable headers to make it more user friendly when integrating it into projects. If this was for a top level only application simple Male headers would do fine. I repositioned the reset switch to the upper level and added a trimpot for contrast adjustment on the LCD.

The code to run the the LCD with Shift register needs the LCD3Wire Library found Here on the Arduino playground. If you load up the LCD3Wire Example you only need to make a few adjustments to the pinouts.

Standard Library Pins
'
// Arduino pins
#define LCD_LINES 1  // number of lines in your display
#define DOUT_PIN  11  // Dout pin
#define STR_PIN   12  // Strobe pin
#define CLK_PIN   10  // Clock pin
Modified Library Pins
// Arduino pins
#define LCD_LINES 2  // number of lines in your display
#define DOUT_PIN  3  // Dout pin
#define STR_PIN   2  // Strobe pin
#define CLK_PIN   4  // Clock pin
'
Upload the sketch to your Arduino and you should see the example array streaming through the data.
