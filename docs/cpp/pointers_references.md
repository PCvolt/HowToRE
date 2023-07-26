## Pointers and References
A reference is an **alias** of a variable, while a pointer is **a variable holding the address of another variable**.
<br>To be more exact, a reference is still treated as a pointer by the compiler, that automatically dereferences itself when used, is less versatile than a pointer but safer on its uses cases.


### Usage
Use pointers for data structures, address arithmetics and everything else.
<br>Use references for function parameters and return types.

Example with variables:
```c++
void incrementBy(int &a, int b)
{
    a = a + b
}

int main void()
{
    int a = 6;
    int b = 2;

    incrementBy(a, b);
    std::cout << a << std::endl; // prints 8
    return EXIT_SUCCESS;
}
```

Example with a function:
```c++
void printMessage(const std::string& message)
{
    std::cout << message << std::endl;
}

void callFunctionByReference(void (&funcRef)(const std::string&), const std::string& message) {
    funcRef(message);
}

int main() {
    callFunctionByReference(printMessage, "Hello world!");

    return EXIT_SUCCESS;
}
```

### Rules
```c++
int a = 0;

int *ptr = &a; // address of a
int &ref = a; // ref is an alias of a
```
---
**Accessing the value and address**:
```c++
std::cout << *ptr << std::endl; // displays the value of a
std::cout << ref << std::endl; // displays the value of a

std::cout << ptr << std::endl; // displays the address of a
std::cout << &ref << std::endl; // displays the address of a
```
---
**NULL**:
<br>A reference cannot be null, a pointer can be.
<br>A reference must always be initialized.
```c++
 // valid
int *ptr;
int *ptr2 = nullptr;

// not valid
int &ref;
```
---
**Reassignation**:
<br>A reference cannot be reassigned after initialization.
<br>A pointer can be reassigned as many times as you need.
```c++
int a;
int b;

int *ptr = &a;
ptr = &b; // valid

int *ref = a;
ref = b; // not valid
```
---
**Indirection**:
<br>A reference only offers one level of indirection, whereas pointers offer as many as you want.
```c++
int a;
int *ptr = &a;
int **pptr = &ptr; // valid

int &ref = a;
int &&ref = ref; // not valid
```
---
**Address**:
<br>References do not have their own memory space, i.e they don't have an address unlike pointers.