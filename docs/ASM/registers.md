## Registers


A common depiction of the registers is as follow:
| Register | Usage                           |
| -------- | ------------------------------- |
| EAX      | General purposes / return value |
| EBX      | General purposes                |
| ECX      | General purposes                |
| EDX      | General purposes                |
| ESI      | General purposes                |
| EDI      | General purposes                |
| ESP      | Stack Pointer                   |
| EBP      | Base Pointer                    |

- ``EAX`` is a general-purpose register, but is commonly used to store the **return value** of a function
- ``EBX`` to ``EDI`` are general-purposes registers
- ``ESP`` is the **Stack Pointer**, it points to the top of the stack
- ``EBP`` is the **Base Pointer**, it is set at ``ESP`` at the beginning of a function (beginning of a stack frame)
- ``EIP`` is the **Instruction Pointer**, it is a special register which points to the next instruction to execute in the code, useful to look at when using CheatEngine