PicoChess
=========

Modified to work with non DGT boards
Should run on PC, 
Recommend using Pycharm to debug and install requirments.

PicoChess
=========

This is quite a complicated project.
I recommend you do not attempt it unless you have some knowledge of digital electronics, Arduino C programming and Python programming.
Without These skills you will find it difficult to locate any wiring or component errors.

It requires a I2c 20*4 LCD display connected to the arduino via I2c.

Functionality.
To scan the reed switches, The Arduino uses a 4017 chip to set each row in turn  to + 5v, Then reads the columns into the arduino via the shift register. 
It doesn't start to monitor buttons or reed matrix until it detects the pieces are set up to starting chess position, comment out the newgame line in the startup code to bypass this check.
When a reed swith opens or closes the led for that square are flashed.
The arduino also monitors the buttons in the same way.
It sends "B:n" for a button change or move (eg "D2D4") to the pc via the usb port.

To test the board, monitor Arduino serial to make sure it is sending the expected messages.

to start 
python3 picochess.py.

picochess is well documented on the picochess website.

My modifications are 
added sensorboard.py
some changes to picochess.py for the added messages/events
