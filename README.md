# SaintCon2016Badge #
This is instructions to get the SaintCon 2016 badge to work with the Arduino Ide
## Adding the ESP8266 chip to your ardiono ide ##
 1. copy http://arduino.esp8266.com/stable/package_esp8266com_index.json into file -> preferences -> additional boards manager URLs
 2. Go to tools -> boards: -> board manager, find the esp8266 board, click on it and click install
 

 
## Adding the LedControl library to your ide ##
 1. Go to https://github.com/wayoda/LedControl and download the repository
 2. Go to sketch -> include library -> add .zip library, find the download and choose it
 
 
 
#### Try uploading a sketch to the board, I have provided one
#### If you recieve an error containing avr/pgmspace.h then continue following the instructions, otherwise have fun!
### Fixing the error mentioned above
 1. Click http://download.savannah.gnu.org/releases/avr-libc/avr-libc-2.0.0.tar.bz2 which will download the avr libraries
 2. Once downloaded uncompress the file
 3. Copy the avr-libc-2.0.0/include/avr folder to the src/ folder for the LedControl library
    - If you have linux the directory for the src/ directroy is ~/Arduino/libraries/LedControl/src/
    - Windows and Mac the directory will be in your documents folder under Arduino/libraries/LedControl/src/
 4. Then in the src/ directory you just put the avr/ folder change the following lines to the LedControl.h file
~~~
#if defined (ESP8266)
#include <pgmspace.h>
#else
#include <avr/pgmspace.h>
#endif
~~~
~~~
This should replace the #include <avr/pgmspace.h> line
~~~

    
