<div style="font-size: 17px;background: black;padding: 2rem;">

Lambda functions (also known simply as "lambdas") are a type of anonymous function that you can define within your code. Introduced in C++11, they allow you to create small, inline function objects without needing to give them a name. Lambdas are particularly useful for short, throwaway functions that are used in algorithms or for callback functions.

<h3><u>Basic Syntax:</u></h3>

```c++
[capture](parameters) -> return_type {
    // function body
};
```

- <b style="color: Salmon;">Capture list:</b> This specifies which variables from the surrounding scope are available to the lambda function. It’s enclosed in square brackets [].
- <b style="color: Salmon;">Parameters:</b> This is the list of parameters for the lambda, just like any other function.
- <b style="color: Salmon;">Return type:</b> This is the return type of the lambda function. It can be omitted if it can be inferred.
- <b style="color: Salmon;">Function body:</b> This is the code that executes when the lambda is called.

Generally, the `return_type` in lambda expressions is evaluated by the compiler itself and we don’t need to specify it explicitly. Also the `-> return_type` part can be ignored. However, in some complex cases e.g. conditional statements, the compiler can’t determine the return type and explicit specification is required.

<h3><u>Example code</u></h3>

```c++
auto add = [](int a, int b) -> int {
    return a + b;
};

int result = add(3, 4); // result is 7
```

<h3><u>Capturing external variables</u></h3>

- <b style="color: Chartreuse;">[&]</b> : Capture all external variables by reference.
- <b style="color: Chartreuse;">[=]</b> : Capture all external variables by value.
- <b style="color: Chartreuse;">[a, &b]</b> : Capture a by value and b by reference.

```c++
int x = 10;
int y = 20;

auto byValue = [=]() { return x + y; }; // Capture by value
auto byReference = [&]() { x = x + y; }; // Capture by reference

int result1 = byValue(); // result1 is 30
byReference();
int result2 = x; // result2 is 30, x is now 30
```

<span style="color: Cyan;">A lambda with an empty capture clause [ ] can only access variables which are local to it.</span>

<h3><u>Mutable lambdas</u></h3>

By default, lambdas that capture variables by value cannot modify those variables. If you need to modify captured values, you can use the `mutable` keyword.

```c++
int z = 5;
auto increment = [z]() mutable { z++; return z; };

int new_z = increment(); // new_z is 6, but original z remains 5
```

<h3><u>Generic lambdas</u></h3>

Introduced in C++14, lambdas can have templated parameters to make them more flexible.

```c++
auto genericAdd = [](auto a, auto b) {
    return a + b;
};

int intSum = genericAdd(1, 2); // intSum is 3
double doubleSum = genericAdd(1.5, 2.5); // doubleSum is 4.0
```

<h3><u>Practical usecase</u></h3>

Lambdas are often used in standard library algorithms, such as `std::sort`, `std::for_each`, etc., to provide custom operations without having to define separate named function objects.

```c++
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> vec = {4, 2, 3, 1};
    std::sort(vec.begin(), vec.end(), [](int a, int b) { return a < b; });

    for (int v : vec) {
        std::cout << v << " "; // Outputs: 1 2 3 4
    }

    return 0;
}
```

In this example, a lambda is used as the comparison function for `std::sort`.

Lambdas make code more concise and easier to read, especially for simple operations that are used locally within a function or algorithm. They are a powerful feature in modern C++ that enhances the expressiveness and flexibility of the language.

</div>

<!-- <div style="font-size: 17px;background: black;padding: 2rem;"> -->
<!-- <div style="background: DarkRed;padding: 0.3rem 0.8rem;"> [HIGHLIGHT] -->
<!-- <h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;"> [SUBHEADING] -->
<!-- <b style="color: Chartreuse;"> [NOTE] -->
<!-- <b style="color:red;"> [NOTE-2] -->
<!-- <span style="color: Cyan;"> [IMP] -></span> -->
<!-- <b style="color: Salmon;"> [POINT] -->
<!-- <div style="border: 1px solid yellow; padding: 10px;"> [BORDER] -->
