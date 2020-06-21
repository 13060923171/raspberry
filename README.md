# raspberry
怎么用树莓派的GPIO控制灯的闪烁

![](https://s1.ax1x.com/2020/06/21/N3YgOI.png)2、我们还要准备一块面包板一个1K的电阻和一个led灯![2](https://s1.ax1x.com/2020/06/21/N3YO00.png)

3、源代码

```python
import RPi.GPIO as GPIO # Import Raspberry Pi GPIO library
from time import sleep # Import the sleep function from the time module
 
GPIO.setwarnings(False) # Ignore warning for now
GPIO.setmode(GPIO.BOARD) # Use physical pin numbering
GPIO.setup(8, GPIO.OUT, initial=GPIO.LOW) # Set pin 8 to be an output pin and set initial value to low (off)
 
while True: # Run forever
GPIO.output(8, GPIO.HIGH) # Turn on
sleep(1) # Sleep for 1 second
GPIO.output(8, GPIO.LOW) # Turn off
sleep(1) # Sleep for 1 second
 
```

