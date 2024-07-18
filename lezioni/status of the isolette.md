State: off, fail, idle, param, operational, alarm

Which kind of allarm?
- Silent and Soft alarm (like when the isoless has just beed started)
- Hard alarm (like a termomiter is broken) - > fail state

Nurse <-> Isolette <-> air -> baby

The isolette can only heat the air, only one control action. The feedback is the termperature of the air. We could even ignore that there is a baby (we don't know how the baby in interacting with the air).

Air has also external influence like: 
- room temperature
- the baby


# Isolette

1 control action: read the temperature and the feedback will be the temperature of the air -> The are multiple tempometer.

There are more than one electrical heating surfeces, basically a wire where we can apply a difference of potential and the wire will heat up. With a resistor we can check if no current is flowing, by placing a voltmeter we have a feedback from the heating surfaces.

We have user interface devices for comunicating with the nurse.

# CTL

Controller, it has a control algoritm inside, a process model as well.

process model -> what I am duing now, what I belive what the rest of the system is duing now.

- The CTL control the THM module that is in charge of controlling the thermometer.
- THe CTL control the HTR module hat is in charge of controlling the heating surfaces.
- The CTL control the UI module that is in charge of the user interface (nurse interact with)

Each module is a software module.