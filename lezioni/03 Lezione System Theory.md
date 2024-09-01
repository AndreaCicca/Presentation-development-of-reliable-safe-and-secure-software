# System theory

System that has a lot of interactive components, Too complex for complete analysis and Too organized for statistics.
The focus is on the system taken as a whole, not on the individual components (The whole is greater than the sum of its parts). We find Emergent properties that arise from complex interactions.

System theory is based on a simple component: A process and a **controller** that obtain feedback from the process and use it to control the process. 
The controller ensure safety constraint like power mist never be on when access door is open. [link](https://en.wikipedia.org/wiki/Systems_theory)

Treating safety as a **control problem**, we don't prevent failures, we enforce safety constraints.

## Treating Safety as a Control Problem

A controller contains a Control algorithm and a Process model.

Control algorithm: A set of rules that determine the behavior of the controller.

Controller -> Control Actions -> Controlled process
Controlled process -> Feedback -> Controller

Controllers use a process model to determine control actions.
Controller control actions via controller process and (via actuators) and receive feedback from the Controlled Process (via sensors). The controller can't be sure that the process model is correct, and the controller can't be sure that the sensors are working properly.

Software/human related accidents often occur when the process model is incorrect

We can have multiple levels of control module, for example in the Missile Release Mishap there were 4 levels: Command Authority <-> Pilot <-> Software Controller <-> Aircraft.

### Example

Mars Polar lander: Process model was wrong, the computer system believe that the lander had landed, but it wasn't true. A problem in the feedback (the lander wasn't landed).

# STAMP Approach

STAMP: System-Theoretic Accident Model and Processes
Identify potentially unsafe control actions -> Identify why they might be given -> If safe ones provided, then why not followed?

A new, more powerful accident/loss causality model based on systems theory, not reliability theory, Defines accidents/losses as a dynamic control problem (vs. a failure problem). Applies to VERY complex systems.

## Goal: Design an effective control structure that eliminates or reduces adverse events

- Need clear definition of expectations, responsibilities,
authority, and accountability at all levels of safety control
structure
- Need appropriate feedback
- Entire control structure must together enforce the system safety property (constraints):
    • Physical design (inherent safety)
    • Operations
    • Management
    • Social interactions and culture 146


## Basic control loop

- Control actions are provided to
affect a controlled process
- Feedback may be used to
monitor the process
- Process model (beliefs) formed
based on feedback and other
information
- Control algorithm determines
appropriate control actions given
current beliefs

**STAMP Model- > Accidents are caused by inadequate control**

Cast Accident analysis: How do we find inadequate control that caused a previous accident?

**STRPA Hazard analysis: How do we find inadequate control that could cause a future accident?**

- STPA: Methodology
- STAMP: Theory (safety, security, etc. is a control problem)

## System-Theoretic Process Analysis (STPA)

STPA can help anticipate hazardous scenarios caused by:
- Software, computers, and automation
- Human error/confusion
- System design errors
- Flawed assumptions
- Missing design requirements
- Interactions between systems

Step 1: What is the system and what is the environment? (system boundary)
Step 2: Model
Step 3: Behavior to prevent
Step 4: How could behavior occur feedback loop


STPA identify unsafe control actions:
- Not provided causes hazards ( Controller X shall provide command Y when D)
- Providing causes hazards (Controller X shall not provide command Y when D)
- Too early, too late, out of order (Controller X shall provide command Y within F seconds of G)
- Stopped too soon, applied too long (Controller X shall stop providing command Y within H seconds of J)

Hight level safety constraints: Controller X shall not allow A, Controller Shall enforce B.

Traceability is maintained throughout. 

From System hazard to System requirements is just an act of negation.

For example:
H-1: Vehicle does not maintain safe distance from nearby objects -> R-1: Vehicle must maintain safe distance from nearby objects