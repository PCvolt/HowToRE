## Smart Pointers (C++11)
We will focus on **heap-allocated objects**.

### Common problems with raw pointers
Raw pointers do not go out of scope, therefore are not destroyed automatically, this causes:

- Memory leaks: the user forgets to ``delete`` and the memory can overflow
- Dangling pointers: a pointer points to an address that has been deallocated
- Wild pointers: a pointer may have not been initialized to point to a valid address or object

*``delete`` calls the destructor of the object first then deallocate the memory the pointer was pointing to*

When allocated in the heap, the object can take as much memory as the OS can provide, and must be manually ``deleted``.
```c++
Class *obj = new Class(); // allocated in the heap
```

When allocated in the stack, the object is destroyed when going out of scope, but is limited to the size of the stack itself (a few Megabytes).
<br>Stack-allocated objects are typically used when they won't live beyond the scope of the current function.
```c++
Class obj(); // allocated in the stack
```
---
### How Smart Pointers solve these issues
*Include ``#include <memory>`` to use smart pointers.*

Smart pointers are pointers that are self-managed, that is to say they will ``delete`` when:

- they go out of scope
- they call ``reset()``

However, smart pointers are mostly used with heap-allocated objects as the stack has its own rules of ownership and deallocation.

---
### std::unique_ptr (deprecates auto_ptr)
A ``unique_ptr``  has exclusive ownership of a dynamically allocated object.
<br>If another pointer tries to copy or assign itself to the object, the compiler will raise an error.
<br>Has less overhead than shared_ptr and usually more efficient.

```c++
auto obj = std::make_unique<Class>();
```

### std::shared_ptr
A ``shared_ptr`` allows multiple smart pointers to share the ownership of the object, and keeps track of how many smart pointers are pointing towards the object with ``use_count()``.

```c++
auto obj = std::make_shared<Class>();
```

### std::weak_ptr
Typically used to break circular dependency of shared pointers. Otherwise not very common.

```c++
auto obj = std::make_weak<Class>();
```