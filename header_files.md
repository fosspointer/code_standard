# Header Files

- All header files must use the `".hpp"` file extension. Do not use alternatives such as `".h"`, `".hh"`, `".h++"`, etc...

- All header files must use the `#pragma once` directive instead of a traditional include guards.
```c++
// Don't do this
#ifndef HEADER_HPP
#define HEADER_HPP
...
#endif

// Do this instead
#pragma once
...
```
- Every code structure (classes/functions/etc...) has to be inside of the appropriate namespace (one for the project name, optionally one for the submodule).
```c++
// Don't do this
void foo(); void bar();

// Do this instead
namespace myProject // Optionally myProject::fooBarStuff 
{
    void foo(); void bar();
}
```
- Generally, every header should be focused on one class/namespace.
```c++
// Don't do this
AandB.hpp
---
class A {...};
class B {...};

// This is better
A.hpp
---
class A{...};

B.hpp
---
class B{...};
```
- Do not explicitly include headers that are already included (implicitly/explicitly).
```c++
// Don't do this
#include <my_project/system.hpp> // Includes hello.hpp and world.hpp
#include <my_project/system/hello.hpp>
#include <my_project/system/world.hpp>

// Do this instead
#include <my_project/system.hpp> // The rest is already included
```

- All include directives must be placed in the following order: 
```c++
// STD
#include <variant>
#include <functional>
// External libraries
#include <SomeExternalLibrary.hpp>
// Files of the working project
#include <CodeStandard.hpp>
```