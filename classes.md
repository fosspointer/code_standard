# Classes/Structures

- Classes should be used when visibility specifiers are used. If not, using structures is more appropriate.

- All fields must be declared last. Similarly, constructors, destructors and operators must be declared first.

Class specific guidelines:

- In classes, fields must, in most cases, not be exposed directly, being accessed by getters and setters instead. 

- If a non-primitive private field is to be accessed, an immutable reference getter is required. Optionally, a mutable reference getter can also be provided. Setters have to take mutable references.

- If a primitive private field is to be accessed, its getter should, in most cases, return a copy. Setters have to take by-value copies. However, it can also be treated like non-primitives.

- If a getter or setter only performs simple non-conditional code, it can be defined as inline.

- Public fields are accessed directly, without any getters/setters.
```c++
class MyClass
{
public:
    ...
    void setSimpleField(int simple_field) {...} // OK, int is a primitive type

    void setSimpleField(const int& simple_field) {...} // No reason to do this, since int is 32bit and int& is 64bit

    const int& getSimpleField() const {...} // OK, immutable reference getter used

    int& getSimpleField() {...} // OK, mutable reference getter used

    int getSimpleField() const {...} // Also OK, since int is a primitive type 

    void setComplexField(const ComplexType& complex_field) {...} // OK, ComplexType is not a primitive type

    void setComplexField(ComplexType complex_field) // Not OK, since ComplexType is not a primitive type

    const ComplexType& getComplexField() const {...} // OK, immutable reference getter used

    ComplexType& getComplexField() {...} // OK, mutable reference getter used

    ComplexType getComplexField() const {...} // Not OK, since ComplexType is not a primitive type 
private:
    ComplexType m_complexField;
    int m_simpleField;
};
```