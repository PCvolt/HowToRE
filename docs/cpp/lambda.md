## Lambda Functions
Lambda functions are used for functions that only have a use locally within the function you working in.

```
auto lambda = [captures](parameters)
{
    // content
};
```

The ``captures`` refers to the variables present in the enclosing scope. That is:
```
void function()
{
    int b = 2;
    auto funcionLambda = [&]()
    {
        std::cout << b << std::endl; // can only access b
    };
}


int main()
{
    int a = 1;

    auto mainLambda = [&]()
    {
        std::cout << a << std::endl; // can only access a
    };

    function();
}
```

<br>``[&]`` will capture every variable in the scope by reference.<br>To access a by reference, write ``[&a]``.

``[=]`` will capture every variable in the scope by value.
<br>To access the value of the variable a, write ``[a]``.

Example:
```
void function()
{
    int a = 1;
    int b = 2;
    int c = 3;

    auto computeValueA = [&a, b](int number)
    {
        // a is captured by reference, and b by value
        // c is not captured
        a = a * b + number;
    };

    computeValueA(4) // a is now equel to 1 * 2 + 4 = 6
}
```