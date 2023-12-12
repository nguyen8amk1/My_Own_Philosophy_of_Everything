# STANDARD INPUT AND OUTPUT
notes from blog: https://nus-unix-workshop.github.io/2021-s1/stdio/

## HISTORY
2 of the design decisions (that leads to UNIX simplicity): 
    + DECOUPLE the PHYSICAL input/output DEVICES from the PROGRAM.
        -> Allow the UNIX PROGRAM to READ from ABSTRACT input and output DEVICES
    + MAKE ALL PROGRAMS read and write from these ABSTRACT DEVICES by DEFAULT. 

## 2 ABSTRACT DEVICES that Unix provide is called: 
    + STANDARD INPUT (default: KEYBOARD) 
    + STANDARD OUTPUT (default: TERMINAL)

-> FREES THE PROGRAMMERS from worrying about 
    + WHERE to READ The input FROM 
    + WHERE to WRITE the output TO 
