## Calling Conventions
A Calling Convention indicates how the compiler should:
- give the args to the function CALL
- tell which registers the callee must preserve for the caller
- indicate whether the callee or the caller shoud clean up the stack

``__cdecl`` *is the default convention call for C/C++ programs*
```
returnType function(argn, ..., arg2, arg1)
```
- ``ECX`` and ``EDX`` are general-purposes registers that can be used to pass args
- The other registers can be modified

---
``__stdcall`` *is not the default convention call despite the name "standard call"*
```
returnType function(argn, ..., arg2, arg1)
```
- Does not allow for variable-length arg list

The callee clears the stack before returning (RET 0x4 clears the top 4 bytes on the stack. It doesn't return 4.)

---
``__fastcall``
```
returnType function(arg1, arg2, ..., argn) // args are passed left to right!
```
- The two first args are passed in ``ECX`` and ``EDX`` (if they have the size of a DWORD or below)
- The other args are PUSHed in the stack like other call conventions would do

The callee cleans the stack.

---
``__thiscall`` *is the default convention call for **member methods**, C++ exclusive*
```
returnType function(argn, ..., arg2, *this)
```

- Microsoft Specific
- ``*this`` is passed through ``ECX``
- the other args are passed through the stack

The callee cleans the stack.


---
``unknown``

Sometimes the calling convention used does not correspond to anything used commonly.
<br>In cases like these, you will have to guess on your own how the function is called.

When writing the hook, you will have to type your own ``__declspec(naked)`` function and write in ASM to manage the registers and write the instructions yourself.