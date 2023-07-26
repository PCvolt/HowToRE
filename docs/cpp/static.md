## Static

### Static variable
A static variable are initialized only once and hold the value even when going out of the function. Their lifetime persists through the lifetime of the program itself.

*Global variables have a lifetime that begins before the programs starts! For a static variable, it is only during the execution.*
```c++
void function()
{
    static int count = 0;
    count += 2;
    std::cout << count << std::endl;
} // OUTPUT: 0 2 4 6 8

int main()
{
    for (int i = 0; i < 5; ++i)
        function();
    return EXIT_SUCCESS;
}
```

### Static member variable
A static variable is a variable shared among all the objects of the class. It is not initialized in the constructor, and must be initialized outside of the class.

```c++
class Class 
{
    public:
        static int instancesNumber;
}

int Class:instancesNumber = 0;
```

### Static member function
A static function is a function associated to the Class itself rather than its objects. As such, static functions can only manipulate static variables, but such functions can be called even without an instance of the Class!

```c++
class Class 
{
    public:
        static int number;

        static void incrementNumber()
        {
            number += 1;
        }
}

// The initialization is made outside the main
// Else, each time function would be called, it would reset to 50
// This holds for main() as well, for good practice measures
int Class:number = 50;

int function()
{
    Class:incrementNumber();
}
```

Note that static function do not have access to the ``this`` pointer.