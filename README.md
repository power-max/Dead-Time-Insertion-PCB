# Dead Time Insertion PCB

This KiCad PCB module is designed to take a single-ended TTL level square wave signal from some source and create a sort of "complementary output" but with the propagation delay for the rising edge signal delayed significantly more than the falling edge (or the opposite case if the output is inverted). This allows for driving the high and low side of a half bridge to ensure break-before-make condition.

The pinout of the 0.1 pin header has several options.

## Pin 1 (DEADTIME_CTRL)
This pin allows a current source to control the amount of deadtime that this circuit implements. It simply feeds a current mirror. A lower current will allow for a slower discharge of C5 and C6, which concequentally lead to increased the deadtime. The unfortunate side-effect is this also increases the propagation delay for signals propagating throught this block, particularly for changing the state of switching ON the switching element. Perhaps there is a way to beat causality? please let me know!

## Pin 2 (INPUT)
This is the single TTL level square wave input that is to be converted to a complimentary output for the half bridge.

## Pin 3 (INVERT)
Invert output allows the output pins 7 and 8 to be inverted, such as may be required if you are using an inverted input gate driver IC. Set this HIGH if you wish to use inverting FET driver IC.

## Pin 4 (~EN) 
This is just an ENABLE. The outputs are held at whatever the respective LOW state would be depending on the state of Pin 3, ensuring both Hi and Lo side FETs remain OFF.

## Pin 5 (VCC)
power for the circuit. Added an LDO regulator footprint (SOT-89) to the circuit, would recommend an LDO to allow operation down to around 3V depending on output voltage requirements and input voltage range.

## Pin 6 (GND)
GND, RTN, or COM. Whatever you prefer to call it.

## Pin 7 (OUT_L)
This is the output intended for the LO-side switching element gate driver.

## Pin 8 (OUT_H)
This is the output intended for the HI-side switching element gate driver.
