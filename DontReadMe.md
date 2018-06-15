========================
**Python For Micro:bit**
========================            
    
**Sleep for the given number of milliseconds.**

::

 sleep(ms)


**Returns the number of milliseconds since the micro:bit was last switched on.**

::

 running_time()

**Makes the micro:bit enter panic mode (this usually happens when the DAL runs out of memory, and causes a sad face to be drawn on the display). The error code can be any arbitrary integer value.**

::

 panic(error_code)

**resets the micro:bit.**

::

 reset()

Button
~~~~~~

**Returns True or False to indicate if the button is pressed at the time of the method call.**

::

 button.is_pressed()

**Returns True or False to indicate if the button was pressed since the device started or the last time this method was called.**

::

 button.was_pressed()

**Returns the running total of button presses, and resets this counter to zero**

::

 button.get_presses()

LED Display
~~~~~~~~~~~

**Gets the brightness of the pixel (x,y). Brightness can be from 0 (the pixel is off) to 9 (the pixel is at maximum brightness).**

::

 display.get_pixel(x, y)

**Sets the brightness of the pixel (x,y) to val (between 0 [off] and 9 [max brightness], inclusive).**

::

 display.set_pixel(x, y, val)

**Clears the display.**

::

 display.clear()

**Shows the image.**

::

 display.show(image, delay=0, wait=True, loop=False, clear=False)

**Shows each image or letter in the iterable, with delay ms. in between each.**

::

 display.show(iterable, delay=400, wait=True, loop=False, clear=False)

**Scrolls a string across the display (more exciting than display.show for written messages).**

::

 display.scroll(string, delay=400)

Pins
~~~~

**Value can be 0, 1, False, True**

::

 pin.write_digital(value)

**Returns either 1 or 0**

::

 pin.read_digital()

**Value is between 0 and 1023**

::

 pin.write_analog(value)

**Returns an integer between 0 and 1023**

::

 pin.read_analog()

**Sets the period of the PWM output of the pin in milliseconds (see https://en.wikipedia.org/wiki/Pulse-width_modulation)**

::

 pin.set_analog_period(int)

**Sets the period of the PWM output of the pin in microseconds (see https://en.wikipedia.org/wiki/Pulse-width_modulation)**

::

 pin.set_analog_period_microseconds(int)

**Returns boolean**

::

 pin.is_touched()

Images
~~~~~~

**Creates an empty 5x5 image**

::

 image = Image()

**Create an image from a string - each character in the string represents an LED - 0 (or space) is off and 9 is maximum brightness. The colon ":" indicates the end of a line.**

::

 image = Image('90009:09090:00900:09090:90009:')

**Create an empty image of given size**

::

 image = Image(width, height)

**Initializes an Image with the specified width and height. The buffer should be an array of length width * height**

::

 image = Image(width, height, buffer)

**Methods**
**Returns the image's width (most often 5)**

::

 image.width()

**Returns the image's height (most often 5)**

::

 image.height()

**Sets the pixel at the specified position (between 0 and 9). May fail for constant images.**

::

 image.set_pixel(x, y, value)

**Gets the pixel at the specified position (between 0 and 9)**

::

 image.get_pixel(x, y)

**Returns a new image created by shifting the picture left 'n' times.**

::

 image.shift_left(n)

**Returns a new image created by shifting the picture right 'n' times.**

::

 image.shift_right(n)

**Returns a new image created by shifting the picture up 'n' times.**

::

 image.shift_up(n)

**Returns a new image created by shifting the picture down 'n' times.**

::

 image.shift_down(n)

**Get a compact string representation of the image**

::

 repr(image)

**Get a more readable string representation of the image**

::

 str(image)

**Operators**
**Returns a new image created by superimposing the two images**

::

 image + image

**Returns a new image created by multiplying the brightness of each pixel by n**

::

 image * n

**Built-in images.**

::

 Image.HEART
 Image.HEART_SMALL
 Image.HAPPY
 Image.SMILE
 Image.SAD
 Image.CONFUSED
 Image.ANGRY
 Image.ASLEEP
 Image.SURPRISED
 Image.SILLY
 Image.FABULOUS
 Image.MEH
 Image.YES
 Image.NO
 Image.CLOCK12 # clock at 12 o' clock
 Image.CLOCK11
 ... # many clocks (Image.CLOCKn)
 Image.CLOCK1 # clock at 1 o'clock
 Image.ARROW_N
 ... # arrows pointing N, NE, E, SE, S, SW, W, NW (microbit.Image.ARROW_direction)
 Image.ARROW_NW
 Image.TRIANGLE
 Image.TRIANGLE_LEFT
 Image.CHESSBOARD
 Image.DIAMOND
 Image.DIAMOND_SMALL
 Image.SQUARE
 Image.SQUARE_SMALL
 Image.RABBIT
 Image.COW
 Image.MUSIC_CROTCHET
 Image.MUSIC_QUAVER
 Image.MUSIC_QUAVERS
 Image.PITCHFORK
 Image.XMAS
 Image.PACMAN
 Image.TARGET
 Image.TSHIRT
 Image.ROLLERSKATE
 Image.DUCK
 Image.HOUSE
 Image.TORTOISE
 Image.BUTTERFLY
 Image.STICKFIGURE 
 Image.GHOST
 Image.SWORD
 Image.GIRAFFE
 Image.SKULL
 Image.UMBRELLA
 Image.SNAKE

**Built-in lists - useful for animations, e.g. display.show(Image.ALL_CLOCKS)**

::
 
 Image.ALL_CLOCKS
 Image.ALL_ARROWS 

The accelerometer
~~~~~~~~~~~~~~~~~

**Read the X axis of the device. Measured in milli-g.**

::

 accelerometer.get_x()

**Read the Y axis of the device. Measured in milli-g.**

::

 accelerometer.get_y()

**Read the Z axis of the device. Measured in milli-g.**

::

 accelerometer.get_z()

**Get tuple of all three X, Y and Z readings (listed in that order).**

::

 accelerometer.get_values()

**Return the name of the current gesture.**

::

 accelerometer.current_gesture()

**Return True or False to indicate if the named gesture is currently active.**

::

 accelerometer.is_gesture(name)

**Return True or False to indicate if the named gesture was active since the last call.**

::

 accelerometer.was_gesture(name)

**Return a tuple of the gesture history. The most recent is listed last.**

::
 
 accelerometer.get_gestures()

The compass
~~~~~~~~~~~
**Calibrate the compass (this is needed to get accurate readings).**

::

 compass.calibrate()

**Return a numeric indication of degrees offset from "north".**

::
 
 compass.heading()

**Return an numeric indication of the strength of magnetic field around the micro:bit.**

::

 compass.get_field_strength()

**Returns True or False to indicate if the compass is calibrated.**

::

 compass.is_calibrated()

**Resets the compass to a pre-calibration state.**

::

 compass.clear_calibration()

I2C bus
~~~~~~~
**Read n bytes from device with addr; repeat=True means a stop bit won't be sent.**

::

 i2c.read(addr, n, repeat=False)

**Write buf to device with addr; repeat=True means a stop bit won't be sent.**

::

 i2c.write(addr, buf, repeat=False)

UART
~~~~
**Set up communication (use pins 0 [TX] and 1 [RX]) with a baud rate of 9600.**

::

 uart.init()

**Return True or False to indicate if there are incoming characters waiting to be read.**

::

 uart.any()

**Return (read) n incoming characters.**

::

 uart.read(n)

**Return (read) as much incoming data as possible.**

::

 uart.readall()

**Return (read) all the characters to a newline character is reached.**

::

 uart.readline()

**Read bytes into the referenced buffer.**

::

 uart.readinto(buffer)

**Write bytes from the buffer to the connected device.**

::

 uart.write(buffer)
