Raspberry Pi Workshop
=====================

Welcome
TODO: Welcome image


GPIOs
=====

- General purpose input/output pins
- Raspberry Pi has a whole set of them, each with a different purpose

<TODO include GPIO image


A basic circuit
===============
- Take your LED
- Attach each end to female-female lead.
- Long end to red, short end to resistor, that resistor to black
- Red to pin 2
- Black to pin 6
- Apply power

<TODO Image of the result


Interaction through code
========================
- Remove power
- Reattach the red lead to pin 3

- Setup your pi:

sudo apt-get install python-dev
sudo apt-get install python-rpi.gpio

- Create a python program with the following code:

```python

import time
import RPi.GPIO as GPIO

output_pin = 3  # The pin that the output is attached to.

# Set the mode of the GPIO output pi to output
GPIO.setmode(GPIO.BCM)
GPIO.setup(output_pin, GPIO.OUT)

# Loop 10 times, turning light on and off each loop
for i in range(10):
    # turn on
	GPIO.output(output_pin,True)
	time.sleep(2)
	# turn off
	GPIO.output(output_pin,False)
	time.sleep(2)

print("Done!")

```

Getting input
=============
- Connect a button between pins 16 and 3
- Run the following script:

```python

import RPi.GPIO as GPIO

output_pin = 3
input_pin = 16

GPIO.setmode(GPIO.BCM)
GPIO.setup(output_pin, GPIO.OUT)
GPIO.setup(input_pin, GPIO.IN)

while True:
    if GPIO.input(22):
        GPIO.output(output_pin, True)
    else:
        GPIO.output(output_pin, False)

```

Breadboard
==========
- You get a breadboard!
- Overview how a breadboard works

<TODO: Image of breadboard tracks

Example
=======
<TODO: Image of a breadboarded circuit (more advanced than what we do)

Breakout
========
- Cobbler breakout board to connect pins to breadboard
- Hook it up
- Create a simple breadboard holder

<TODO image of completed version


Revision to our circuit
=======================
- Take a shot at redoing out button-push-led on the breadboard
- Introducing jumper leads (male-male)



