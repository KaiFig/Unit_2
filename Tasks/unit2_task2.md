# Task 2

## List of materials 
1 breadboard 

1 USB cable

1 Arduino Uno version R3

3 LED’s 

8 wires

3 resistors 

```.py
from pyfirmata import Arduino
import time

board =Arduino('/dev/cu.usbserial-10')
print("Communication successfully started")
a=False
b=False
c=False
for i in range(1,9):
   c=not(c)
   if i and i%2==0:
       b=not(b)
   if i and i%4==0:
       a=not(a)
   board.digital[12].write(int(c))
   board.digital[9].write(int(b))
   board.digital[5].write(int(a))
   time.sleep(1)
