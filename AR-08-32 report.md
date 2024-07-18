# TEMPERATURE SENSOR

The Temperature Sensor provides the Current Temperature of the Air in the Isolette to the
Thermostat

Displayer range
Range in F: [68.0..105.0] -> C: [20..40.5]

EA-TS-1: The Current Temperature will be provided to the Thermostat in degrees
Fahrenheit

EA-TS-2: The Current Temperature will be sensed to an accuracy of ±0.1°F.

Rationale: An accuracy of 0.1°F is **necessary to ensure the Thermostat can turn the Heat Source on and off quickly enough** to maintain the Desired Temperature Range.

EA-TS-3: The Current Temperature will cover the range of at least 68.0° to 105.0°F.
Rationale: This is the specified range of operation of the Isolette. The lower end of this
range is useful for **monitoring an Isolette that is warming to the Desired Temperature**
Range. The upper end is greater than the Upper Alarm Temperature **to ensure that the Current Temperature will be sensed across the entire Alarm Temperature Range**.

# HEAT SOURCE.

The Heat Source heats the Air in the Isolette. It is turned on and off by changing the value of the
Heat Control controlled variable. The controlled variables are shown in table A-4. No
environmental assumptions are made.
[Off, On]

# OPERATOR INTERFACE

Operator Settings for the Thermostat and receives Operator Feedback from the Thermostat

## Environmental assumptions associated with the Operator Interface are quite strong (simplifies the manage Operator Interface Function)

The following environmental assumptions are made:
• EA-OI-1: All temperatures will be entered and displayed in degrees Fahrenheit.
Rationale: Minimize the complexity of this example. An actual system would probably
support Celsius or perhaps both Fahrenheit and Celsius

• EA4-OI-2: All temperatures will be set and displayed by the operators in increments of
1°F.

Lower Alarm Temperature
>= 34 [93..98]

Lower Desire Temperature

>= 36 [97..99]

Upper Desire Temperature

<= 38 [98..100]

Upper Alarm Temperature

<= 39 [99..103]

At least 1°F of separation between between Desire and alarm temperatures for both upper and lower range.

• EA-OI-9: The Display Temperature will cover the range of at least 68.0° to 105.0°F.


# SAFETY REQUIREMENTS

Prolonged exposure of Infant to unsafe heat or cold
Classification: catastrophic
Probability: < 10^-9 per hour of operation


SR-1: The Isolette shall include an **independent regulator function** that maintains the
Current Temperature inside the Isolette within the Desired Temperature Range.

Allowed probability of failure: <10-5 per hour
• SR-2: The Isolette shall include an **independent monitor function** that activates an Alarm
within a maximum of 5 seconds whenever
    - the Current Temperature falls below or rises above the Alarm Temperature
    Range.
    - the Current Temperature or the Alarm Temperature Range is flagged as invalid.
    - an internal failure has been detected in the monitor function.
  
Rationale: The Alarm Temperature Range will be set by the Nurse based on the Infant’s
weight and health. The Infant should be removed from the Isolette within **15 seconds after the Current Temperature falls below or rises above this range**. With the normal
monitoring provided by the Nurse, this can be accomplished within 10 seconds, leaving 5
seconds for the system to activate the Alarm. Activating the Alarm in less time is
desirable.

If the Current Temperature or the Alarm Temperature Range provided to the monitor
function are flagged as invalid or if an internal failure is detected in the monitor function,
the monitor function should not be trusted to perform correctly.
Allowed probability of failure: <10^-5 per hour.


# THERMOSTAT SYSTEM FUNCTION

The Thermostat performs **two logically independent functions**. The first regulates the Current Temperature in the Isolette so it is maintained within the Desired Temperature Range. 
The second monitors the Current Temperature in the Isolette and activates an Alarm if it falls below
or rises above the Alarm Temperature Range.

The high-level requirements for the Thermostat Function are as follows:
• REQ-TH-1: The Thermostat shall set the value of the Heat Control.
• REQ-TH-2: The Thermostat Function shall set the value of the Regulator Status.
• REQ-TH-3: The Thermostat shall set the value of the Display Temperature.
• REQ-TH-4: The Thermostat shall set the value of the Alarm Control.
• REQ-TH-5: The Thermostat shall set the value of the Monitor Status.

## REGULATE TEMPERATURE FUNCTION

The Regulate Temperature Function compares the Current Temperature from the Temperature
Sensor with the Desired Temperature Range provided by the Operator Interface and turns the
Heat Source on or off to keep the Current Temperature within the Desired Temperature Range.
It also provides the Display Temperature and the Regulator Status back to the Operator Interface.

REQ-RT-1: The Regulate Temperature Function shall set the value of the Heat Control
REQ-RT-2: The Regulate Temperature Function shall set the value of the Regulator
Status.
REQ-RT-3: The Regulate Temperature Function shall set the value of the Display
Temperature.

### Manage Regulator Interface Function

The Manage Regulator Interface Function defines the **interaction with the Operator Interface external entity**. These include **obtaining the Desired Range, reporting back the status of the Regulate Temperature Function, and reporting back the Display Temperature**. The constants are
shown in table A-8.

Status: 
[Init, Normal,Fauled]

The requirements for the Regulator Status controlled variable are as follows:
• REQ-MRI-1: If the Regulator Mode is INIT, the Regulator Status shall be set to Init.
• REQ-MRI-2: If the Regulator Mode is NORMAL, the Regulator Status shall be set to
On.
• REQ-MRI-3: If the Regulator Mode is FAILED, the Regulator Status shall be set to
Failed.

The requirements for the **Display Temperature controlled variable** are as follows:

REQ-MRI-4: If the Regulator Mode is NORMAL, the Display Temperature shall be set
to the value of the Current Temperature rounded to the nearest integer.

**When combined with the accuracy of the Temperature Sensor (EA-TS-2), the Display Temperature should be within 0.6°F of the actual value**

REQ-MRI-5: If the Regulator Mode is not NORMAL, the value of the Display
Temperature is UNSPECIFIED

Desired Temperature is Invalid, the **Regulator Interface Failure shall be set to True**.

[True, False] Indicates an internal failure

REQ-MRI-6: If the Status attribute of the Lower Desired Temperature or the Upper
Desired Temperature is Invalid, the Regulator Interface Failure shall be set to True.

REQ-MRI-7: If the Status attribute of the Lower Desired Temperature and the Upper
Desired Temperature is Valid, the Regulator Interface Failure shall be set to False.

The requirements for the **Desired Range internal variable** are as follows:

[True, False]

REQ-MRI-8: If the Regulator Interface Failure is False, the Desired Range shall be set to
the Desired Temperature Range.

REQ-MRI-9: If the Regulator Interface Failure is True, the Desired Range is
UNSPECIFIED.