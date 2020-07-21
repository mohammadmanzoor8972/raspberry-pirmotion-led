# raspberry-pirmotion-led
Raspberry Pi3 program access Motion and LED
It is Python based application where Used Raspberry Pi 3b+ and Motion sensor. 

## PIR Motion Sensor
* PIR sensor is used for detecting infrared heat radiations. This makes them useful in the detection of moving living objects that emit infrared heat radiations.
* The output (in terms of voltage) of PIR sensor is high when it senses motion; whereas it is low when there is no motion (stationary object or no object).
* PIR sensors are used in many applications like for room light control using human detection, human motion detection for security purpose at home, etc.

### Diagram 
![Raspberry Logo](/PIR%20Interface%20with%20Raspberry.png)

### Source Code in python
```
import RPi.GPIO as GPIO

PIR_input = 29				#read PIR Output
LED = 32				#LED for signalling motion detected	
GPIO.setwarnings(False)
GPIO.setmode(GPIO.BOARD)		#choose pin no. system
GPIO.setup(PIR_input, GPIO.IN)	
GPIO.setup(LED, GPIO.OUT)
GPIO.output(LED, GPIO.LOW)

while True:
#when motion detected turn on LED
    if(GPIO.input(PIR_input)):
        GPIO.output(LED, GPIO.HIGH)
    else:
        GPIO.output(LED, GPIO.LOW)
```

