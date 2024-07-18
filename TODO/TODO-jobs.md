AC -> Nurces
AC -> Logging: git grep log or git grep LOG-> boost library log

for ignoring upper and lowe git grep -i

find logging.h and logging.c

https://github.com/boostorg/log?tab=readme-ov-file for me

fond .log file

preliminary report

-------------------------------------------------------


# Personal TODO list

Logging

- log of each temometer should be on trace lavel
- create a simple tutorial in the pater (appendix)
- explain the difference between loging level


# Program Documentation 

How we document the program, all sources of documentations.


# CTL Requirement

HL Requirement:
- What they are the system function and why at hight level

LL Requirement:
- How (in a software independent way)

## What we have to change

- add storing (and acquiring from the UI) variables for the temperature range requirements (check CTL current implementation)
- adding states for the CTL requirements with a list.
  - selftest
  - notification of the self test
  - enter temperatures rage
    - for each imput a different substate (CTL intelligence for checking safety)

- Handle buttons

# Hardware abstruction layer 

Understand what is an Isolet in a software lavel, in our enviroment the Isolet is a C code and the Simulation in C++.

## Commit Comments

In maiuscolo, il punto e busogna spiegare bene cosa si sta facendo.


Final TODO list

1. Program documentation AC
2. Comparison with FAA (Requirements)
3. MISRA C:2012
4. Logging
5. Doxygen
6. FAA Study 3