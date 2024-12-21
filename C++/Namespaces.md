<div style="font-size: 17px;background: black;padding: 2rem;">

Namespaces in C++ are a feature designed to help organize and manage the scope of identifiers such as variables, functions, classes, and other user-defined types. They help avoid name conflicts in larger projects by grouping logically related identifiers under a unique name.

We can create a namespace by using the <b style="color: Chartreuse;">namespace</b> keyword and declaring/defining our entities within its scope:

```c++
namespace dbl {
    double var;
}
```

Here, we have created a namespace named `dbl` and declared a `double` variable named `var` inside it.

We can then use the `scope resolution operator ::` outside the namespace to specify that we are using the `var` variable belonging to `dbl`.

```c++
dbl::var;
```

Demonstration:

```c++
#include <iostream>
using namespace std;

// create a namespace with a double variable
namespace dbl {
    double var;
}

int main() {
    
    // create an int variable of the same name
    int var = 5;
    
    // use the created namespace to avoid naming conflict
    dbl::var = 5.55;
    
    // display the variables
    cout << "dbl var = " << dbl::var << endl; // dbl var = 5.55
    cout << "main var = " << var << endl; // main var = 5
    
    return 0;
}
```

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Nested Namespaces</h3>

Namespaces can be nested within other namespaces to provide additional levels of organization.

```c++
namespace OuterNamespace {
    namespace InnerNamespace {
        int myVar;
        void myFunction() {
            // function implementation
        }
    }
}

int main() {
    OuterNamespace::InnerNamespace::myVar = 10;
    OuterNamespace::InnerNamespace::myFunction();
    return 0;
}
```

<h3 style="color: Violet;">We can split the definition of namespace over several units.</h3>

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Using Directive</h3>

We can bypass the use of :: operator with the help of the <b style="color: Hotpink;">using</b> directive. In fact, we have been using this directive for the majority of our programs so far with the `using namespace std;` code. We have already mentioned that without the use of the `std` namespace, some of our most important IO objects and standard exceptions become:

```c++
// without using std namespace
std::cout
std::cin
std::endl
std::exception
std::bad_cast
```

By including the `using namespace std;` code in our program, we can omit the `std::` part for the identifiers defined in the std namespace:

```c++
// using std namespace
cout
cin
endl
exception
bad_cast
```

This applies to other namespaces as well. Another demonstration:

```c++
#include <iostream>
using namespace std;

namespace one {

    void display() {
        cout << "namespace one" << endl;
    }
}

namespace two {

    void display() {
        cout << "namespace two" << endl;
    }
}

int main() {

    using namespace one;

    // call one::display()
    display();
    
    // call two:: display
    two::display();
    
    return 0;
}
```

Output:

```
namespace one
namespace two
```

<br>

<div style="border: 2px solid Green; padding: 10px;">

We have included our `using namespace one;` directive inside `main()`, while the `using namespace std;` code is outside of `main()` (and all other possible scopes). This means that we have used the `one` namespace within the scope of the `main()` function, while the `std` namespace is being used in a global scope. The use of a namespace can be global or limited to a certain scope. It depends on how we want to use the namespace.

</div>

<br>

The `using` directive can create a lot of naming conflicts in our program: 

- When we use multiple namespaces with the same identifiers.
- When we use same name namespace function and general function.


</div>

<!-- <div style="font-size: 17px;background: black;padding: 2rem;"> -->
<!-- <div style="background: DarkRed;padding: 0.3rem 0.8rem;"> [HIGHLIGHT] -->
<!-- <h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;"> [SUBHEADING] -->
<!-- <b style="color: Chartreuse;"> [NOTE] -->
<!-- <b style="color:red;"> [NOTE-2] -->
<!-- <span style="color: Cyan;"> [IMP] -></span> -->
<!-- <b style="color: Salmon;"> [POINT] -->
<!-- <div style="border: 1px solid yellow; padding: 10px;"> [BORDER] -->