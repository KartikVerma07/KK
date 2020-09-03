# **Smart-Blind-Stick**

## **Idea:**
There are many devices for visually impaired people. This project is also an attempt to develop an aid for visually impaired persons. This project is a smart stick which is capable of detecting any obstacle, detect water and corners and even allow the user to find the stick if anyhow missed by the user by pressing a remote switch. The device is designed with an intention to sort out common issues faced by the blind people while using traditional sticks.

## **Brief Desciption:**
The smart stick is built on Arduino Pro Mini which is small enough to install on a regular stick and has buzzer, LDR sensor, Ultrasonic sensor and a water detector sensor interfaced to it. 
The Arduino sketch manages to detect an obstacle, sense light, and water and invoke alarm on the press of the remote switch. The sketch is written on Arduino IDE.
The stick also has an RF receiver which connects with an RF transmitter that acts as a remote for finding the stick on missing. The remote built on RF transmitter has a switch pressing which, the buzzer installed on the stick is triggered and by the sound of the buzzer a blind person can find the stick.
The ultrasonic sensor detects obstacles and LDR sensor allows determining the lighted and dark places. A water indicator is also installed at the base of the stick which invokes an alarm if the person is going step into any wet place.

## **Brief Functioning:**
### Obstacle detection:-
The obstacle detection is done by the Ultrasonic sensor. For reading data from the ultrasonic sensor, first a pulse has to be sent to the trigger pin of the sensor and then the analog voltage is read from the echo pin. The analog voltage is converted to digital reading using inbuilt ADC channel and converted to distance measurement. If the distance measured by the ultrasonic sensor is detected less than 10 cm, a HIGH pulse is passed at the pin connected to the buzzer. The pulse lasts for an infinite time until the user gets away from the obstacle. 
### Light detection:-
The light detection is done by the LDR sensor and is used to detect the dark places. The sensor connected to a voltage divider circuit output an analog voltage at the interfaced controller pin. The analog voltage is read and digitized using inbuilt ADC channel. The analog Read () function is used to read analog voltage at the controller pin. 
### Water detection:- 
The water indicator circuit operates by triggering the base of the switching transistor. When the stick steps on water, the metal strips are short-circuited by the water triggering a pulse at the base of the transistor. As the transistor is triggered, the VCC at the collector pin is shorted to the ground through emitter pin and a LOW logic is passed at the pin 3 of the Arduino.
### Stick location detection:-
If any how the user loses the stick, he can press the remote switch which set the D3 bit of the RF encoder to HIGH. The same logic is relayed at the D3 bit of the RF decoder and passed to pin 8 of the Arduino. On receiving a HIGH logic at the pin, the Arduino send a pulse at the buzzer which lasts for a variable duration depending upon the distance of the remote from the stick.

## **Components Used:**
- Arduino Pro Mini                      - 10K ohm resistors - 3
- HR-SR04 Ultrasonic Sensor             - HT12D decoder IC
- Buzzer                                - RF receiver
- LDR Sensor                            - HT12E encoder IC
- BC-548 transistor                     - RF Transmitter
- 5K ohm pot                            - tactile switch
- metal strips
