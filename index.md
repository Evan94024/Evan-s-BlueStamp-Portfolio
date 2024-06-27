Rock Paper Scissor Machine


| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Evan L | Greene Middle School | Electrical Engineering | Rising 8th Grader

<!---
**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE

-->

# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/OKKf9Bwz9w0?si=joaem4pDMoSS2EcE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

For my second milestone, I secured the entire circuit to the cardboard base and added the rock, paper and scissors symbols to the servos. one of the greatest challenges I faced was getting the battery to stay in place. While this may not seem difficult, at one point while I was hot glueing the cardboard gaurds for the battery onto the base, I notice there was smoke, and when I looked into the frame I saw that the battery was emmiting smoke and the power wire was melting. I still am not sure what caused this, although it may be due to me leaving the circuit on or somehow short circuiting it. This, along with many other close calls, such as a faulty battery, makes it a miracle that my arduino hasn't been burnt to a crisp yet. Eventualy, I got the circuit right and it hasn't shorted again. next I have to add an LED the indicate that the arduino is on and add an openable base. 

# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/wZV70MqZfsc?si=4fA33KtGGKvFgOIG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

This machine uses an ultrasonic sensor, which, when it detects a change in distance from a solid object through frequently emmited sound waves, moves random servo. The movement of the servo is randomized through the 'random' function in the C++ arduino code. When The ultrasonic sensor detects movement, it tells the Arduino Uno, which sends a signal to a random servo, telling it to move. Everything is linked together by a medium sized breadboard, and is powered by either a 9-volt battery or an alternate electrical device.
I planned to make and test the code, plan out the circuit and check that the servos and ultrasonic sensor work. I faced a few challenges during this milestone one of which was making sure each of the servo wires are wired to the right ports, such as ground and power. 


# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
#include <Servo.h>

volatile long A;

float checkdistance_11_10() {

digitalWrite(11, LOW);

delayMicroseconds(2);

digitalWrite(11, HIGH);

delayMicroseconds(10);

digitalWrite(11, LOW);

float distance = pulseIn(10, HIGH) / 58.00;

delay(10);

return distance;

}

Servo servo_3;

Servo servo_6;

Servo servo_9;

void setup()

{

A = 0;

pinMode(11, OUTPUT); 

pinMode(10, INPUT);

pinMode(12, OUTPUT);

servo_3.attach(3); 

servo_6.attach(6);

servo_9.attach(9);

}

void loop()

{

if (checkdistance_11_10() < 20) {

A = random(0, 4);

switch (A) {

case 1:

tone(12,131);

delay(100);

noTone(12);

servo_3.write(179);

delay(1000);

servo_3.write(90);

delay(500);

break;

case 2:

tone(12,131);

delay(100);

noTone(12);

servo_6.write(179);

delay(1000);

servo_6.write(90);

delay(500);

break;

case 3:

tone(12,131);

delay(100);

noTone(12);

servo_9.write(179);

delay(1000);

servo_9.write(90);

delay(500);

break;

}

}

}

```

<!---

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Tinkercad  | Used to design the circuit | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

-->

# Starter Project: RGB Slider

<iframe width="560" height="315" src="https://www.youtube.com/embed/juAjxWSKfpk?si=qo6yIqo7F9ixu_79" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

This project used a circuit board with 3 potentiometer sliders and an LED attached to it. The potentiometer sliders control the amount of red, green and blue light going into the LED.
Once I soldered the components in place, I needed an alternate power source such as a laptop or wall socket, as the device can't power itself.
