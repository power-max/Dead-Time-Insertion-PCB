#Dead Time Insertion PCB

This KiCad PCB module is designed to take a single-ended TTL level square wave signal from some source and create a sort of "complementary output" but with the propagation delay for the rising edge signal delayed significantly more than the falling edge. This allows for driving the high and low side of a half bridge to ensure break-before-make condition.

The pinout of the 0.1 pin header has several options.

##Pin 1
This pin allows a current source to control the amount of deadtime that this circuit implements. It simply feeds a current mirror. A lower current will allow for a slower discharge of C5 and C6, which concequentally lead to an increased the deadtime, and as a side-effect also increase the propagation delay for the signal propagating throught this block. 

##Pin 2
This is the single TTL level square wave input that is to be converted to a complimentary output for the half bridge.

##Pin 3
Invert output allows the output pins 7 and 8 to be inverted, such as may be required if you are using an inverted input gate driver IC. Set this HIGH if you wish to use inverting FET driver IC.

##Pin 4
This is just an ENABLE. The outputs are held at whatever the respective LOW state would be depending on the state of Pin 3, ensuring both Hi and Lo side FETs remain OFF.

##Pin 7
This is the output intended for the lo-side switching element gate driver.

##Pin 8
This is the output intended for the hi-side switching element gate driver.
