## Member Initializer List
Member Initializer List is a mechanism for initializing the members of a class directly. It also enables initializing const members and references, whereas the constructor cannot.


### Performance
```
class Class
{
    private: 
        // _ is here to signify it is private
        std::string _id;
        std::string _data; 
    
    public:
    Class(const std::string& id, const std::string& data) :
        _id(id)
    {
        this->_data = data;
        // other operations
    }
}
```

Initializing directly with the values in the initializer list is faster than the constructor giving a default initialization then assigning the values.
<br>*Initializing this->_data in the constructor function is slower than in the initializer list.*

You should write:
```
class Class
{
    private: 
        std::string _id;
        std::string _data; 
    
    public:
    Class(const std::string& id, const std::string& data) :
        _id(id),
        _data(data)
    {
        // other operations
    }
}
```
The members initialized in the list are initialized in the order they are written!

### Const members and References
Const variables and references CANNOT be assigned after initialization. That is, it is not possible to do the following: 

```
class Class
{
    private: 
        const int _id;
        int &_ref;
    
    public:
    Class(const int& id)
    {
        _id = id; // not valid
        ref = id; // not valid
    }
}
```

you must do the following:
```
class Class
{
    private: 
        const int _id;
        int &_ref;
    
    public:
    Class(const int& id) :
        _id(id),
        _ref(id)
    {
        //
    }
}

int main()
{
    int id = 20;
    Class obj(id);

    id = 25;
    // id is changed, _ref reflects it and _ref = 25
    // _id is const and does not change (_id = 20)
}
```

### Foot note
``Class obj(x);`` is created on the stack. It will be destroyed when it goes out of scope. Usually the preferred approach.
<br>``Class *obj = new Class(x);`` is created on the heap and must be manually destroyed with ``delete``. Classes created in the heap can take a much larger place than in the stack, but is slower because of memory (de)allocation overhead.