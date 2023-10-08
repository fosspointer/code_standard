# Miscellaneous

- Do not use TABs, always use an indentation of 4 spaces.
- All "label-like" blocks such as goto labels and class visibility specifiers must be left unindented.
```c++
// Don't do this
class MyClass
{
    public:
        MyClass() = default;
};

switch(value)
{
    case firstCase: 
        ...
        break;
    case secondCase:
        ...
        break;
}

// Do this instead
class MyClass
{
public:
    MyClass() = default;
private:
    bool test = false;
};

switch(value)
{
case firstCase:
    ...
    break;
case secondCase:
    ...
    break;
}
```
- Function implementations that have no reason to reside in a header file must be in the relevant implementation file.
- Comments must all be capitalized as are proper sentences.