## Ghidra's naming and how to read them

``FUN_<ADDRESS>``: Function at <address\> 
<br>``DAT_<ADDRESS>``: Data at <address\>
<br>``LAB_<ADDRESS>``: Label at <address\>, it is a function, struct, data or variable that was not defined by the developer themself.

A same ``var`` can be used for different purposes. A bit troublesome.

``0xffffffff`` = -1 in unsigned
<br>``0xbf800000`` = 1 in floating point
<br>``0x3f800000`` = 1 in floating point

## How to rename without getting lost
It is all good being able to navigate in the decompiled code and finding strings, but you need to sort this mess in a human-readable way, for yourself and others.

Hit ``l`` to rename functions, labels, data or variables.
<br>Don't try to rename things you are too unsure of.

``u_<nameOfYourGuess>`` for functions, variables or whatever that you aren't sure of. u_ stands for unknown.