## Ghidra's naming and how to read them

``FUN_<ADDRESS>``: Function at <address\> 
<br>``LAB_<ADDRESS>``: Label at <address\>, can represent a function.
<br>``DAT_<ADDRESS>``: Data at <address\>

A same ``var`` can be used for different purposes. A bit troublesome.

``0xffffffff`` = -1 in unsigned
<br>``0x3f000000`` = -1 in floating point

## How to rename without getting lost
Hit ``l`` to rename functions, labels, data or variables.

``u_<nameOfYourGuess>`` for functions, variables or whatever that you aren't sure of. u_ stands for unknown.

Don't try to rename things you are too unsure of.