# Smart Highway Toll Gate using Raspberry pico

This is the project repository for Smart Highway Toll Gate. Refer to the sections below for configuration, build and deployment instructions.

## Components

* Raspberry pico
* IR sensor
* Servo motor
  
## Program for Raspberry Pico
```py
from machine import Pin, PWM
import utime
MIN = 800000
MAX = 2000000
led = Pin(25,Pin.OUT)
sensor= Pin(16,Pin.IN)

pwm=PWM(Pin(15))
led.low()
pwm.freq(50)
pwm.duty_ns(MIN)
while True:
    if sensor.value()==1:
        print("Active")
        pwm.duty_ns(MAX)
        utime.sleep(1)
    else:
        print("Off")
        pwm.duty_ns(MIN)
        utime.sleep(1)
```

## Circuit Diagram

![Circuit](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjKfY3nCFiIJZXKt0Rfbv7L_N7v2tEjlGgQYhiIuPfLTP87ZdBU541xcKIWjBYAAism2n6onRVydrb_mZNV_ZObwgXPgjkyFpYG_Pp3j2J19rRLGcUG_IGDqL379VcjxJ1JONRfH8lgv2wkHH-T29iQjYuiTl8ZaReh-6JpgnoozPfZgXpFuoff9ctA/s1600/circuit.png)
