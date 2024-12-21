<div style="font-size: 17px;background: black;padding: 2rem;">

A function is a set of statements that takes input, does some specific computation, and produces output. The idea is to put some commonly or repeatedly done tasks together to make a function so that instead of writing the same code again and again for different inputs, we can call this function. In simple terms, a function is a block of code that runs only when it is called. This not only helps in reducing code duplication but also makes the code more readable, maintainable, and easier to debug.

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Function creation</h3>

There are 2 steps involved in creation of function:

- <b style="color: Salmon;">Declaration (or Prototype):</b> Specifies the function's name, return type, and parameters without the actual body. This informs the compiler about the function's existence before its definition or usage.

  ```
  returnType functionName(parameterType1 parameterName1, parameterType2 parameterName2, ...);
  ```

  <span style="color: Cyan;">Writing parameter names in the function declaration is optional but it is necessary to put them in the definition.</span>

- <b style="color: Salmon;">Definition:</b> Provides the actual body of the function, where the code to be executed is written.

  ```
  returnType functionName(parameterType1 parameterName1, parameterType2 parameterName2, ...) {
      // function body
      // statements
  }
  ```

<b style="color:red;">Alert:</b> If a user-defined function is declared after the `main()` function, an error will occur.

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Function call</h3>

Declared functions are not executed immediately. They are "saved for later use", and will be executed later, when they are called. To call a function, write the function's name followed by two parentheses `()` and a semicolon `;`.

```
int result = functionName(argument1, argument2, .....);
```

<br>

<b>EXAMPLE CODE:</b>

```c++
// Online C++ compiler to run C++ program online
#include <iostream>

int add(int, int);

int add(int a, int b) {
 return a + b;
}

int main() {
 int result = add(5, 3); // Calling the function
 std::cout << "Result: " << result << std::endl; // Result: 8
 return 0;
}
```

<b style="color:Orange;">Note:</b> A C/C++ function is generally defined and declared in a single step because the function definition always starts with the function declaration so we do not need to declare it explicitly. That means in above code, we could delete the declaration and code will still work fine.

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Return statement</h3>

The `return statement` returns the flow of the execution to the function from where it is called. As soon as the statement is executed, the flow of the program stops immediately and returns the control from where it was called. The `return statement` may or may not return anything for a void function, but for a non-void function, a return value must be returned.

In C++ one cannot skip the return statement when the methods have a return type. The return statement can be skipped only for `void` types. Example:

```c++
void fun(){
    cout<< "Hello World!";
}

int main(){
    fun();
    return 0;
}
```

But if there is a return statement inside it, then also there will be no problem if the syntax of it will be:

```c++
void fun(){
    cout<< "Hello World!";
    return ;
}
```

<span style="color: Cyan;">This syntax is used in function just as a jump statement in order to break the flow of the function and jump out of it. But if the return statement tries to return a value in a void return type function, that will lead to errors. </span>

For methods that define a return type, the return statement must be immediately followed by the return value of that specified return type.

```
return-type func()
{
    return value;
}
```

<i><b style="color: Violet;">Note:</b> We can only return a single value from a function using return statement. To return multiple values, we can use pointers, structures, classes, etc. Covered later.</i>

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Parameter Passing Techniques</h3>

In C++, data must be sent to functions when they are called in order to perform operations. This data is called parameters or arguments and there are various parameter passing methods available in C++, each with merits and demerits of its own.

<b style="color: Salmon;">Pass by Value:</b> In Pass by Value method, a variable’s actual value is copied and then passed to the function instead of the original variable. As the result, any changes to the parameter inside the function will not affect the variable’s original value outside the function. Althogh it is easy to understand and implement, this method is not so useful for large size of data structures at it involves copying the value. In example codes above, we are passing parameters by value.

<b style="color: Salmon;">Pass by Reference:</b> Here, instead of passing the argument itself, we passes the reference of an argument to the function. This allows the function to change the value of the original argument. Any changes we make to your argument inside your function are reflected in your original argument so we have to be careful while handling data in this method.

```c++
void modifyValue(int& a) {
    a = 20; // This change affects the original argument
}

int main() {
    int x = 10;
    modifyValue(x);
    std::cout << "x: " << x << std::endl; // Output: x: 20
    return 0;
}
```

<b style="color: Salmon;">Pass by Pointer:</b> The pass-by-pointer is very similar to the pass-by-reference method. The only difference is that we pass the raw pointers instead of reference to the function. It means that we pass the address of the argument to the function.

```c++
void modifyValue(int* a) {
    *a = 20; // This change affects the original argument
}

int main() {
    int x = 10;
    modifyValue(&x);
    std::cout << "x: " << x << std::endl; // Output: x: 20
    return 0;
}
```

<b style="color:red;">Note:</b> In C, we use pointers to achieve call-by-reference. In C++, we can either use pointers or references for pass-by-reference.

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Default arguments</h3>

A default argument is a value provided in a function declaration that is automatically assigned by the compiler if the calling function doesn’t provide a value for the argument. In case any value is passed, the default value is overridden.

```c++
int sum(int x, int y, int z = 0, int w = 0) //assigning default values to z,w as 0
{
    return (x + y + z + w);
}

int main()
{
    cout << sum(10, 15) << endl; // 25
    cout << sum(10, 15, 25) << endl; // 50
    cout << sum(10, 15, 25, 30) << endl; // 80
    return 0;
}
```

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Inline Functions</h3>

Inline functions in C++ are a powerful feature that allows the compiler to insert the complete body of the function wherever it is called, instead of performing a regular function call. This can lead to performance improvements by eliminating the overhead associated with function calls, such as saving the current context, jumping to the function's address, and then jumping back. However, inline functions are typically used for small, frequently called functions where the function call overhead would be noticeable.

Syntax:

```
inline return-type function-name(parameters)
{
    // function code
}  
```

Remember, inlining is only a request to the compiler, not a command. The compiler can ignore the request for inlining.  The compiler may not perform inlining if a function: 

- contains a loop. (for, while and do-while) 
- contains static variables. 
- is recursive. 
- return type is other than void, and the return statement doesn’t exist in a function body. 
- contains a switch or goto statement. 

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Recursion</h3>

Recursion in C++ is a programming technique where a function calls itself in order to solve a problem. A recursive function typically has two parts: a <span style="color: Cyan;">base case</span> that stops the recursion and one or more <span style="color: Cyan;">recursive cases</span> that continue the recursion by calling the function itself. Recursion is a powerful tool for solving problems that can be broken down into smaller, similar subproblems.

```c++
// C++ Program to calculate the sum of first N natural numbers using recursion

int nSum(int n)
{
    // base condition to terminate the recursion when N = 0
    if (n == 0) {
        return 0;
    }

    // recursive case / recursive call
    int res = n + nSum(n - 1);

    return res;
}

int main()
{
    int n = 5;

    // calling the function
    int sum = nSum(n);

    cout << "Sum = " << sum;
    return 0;
}
```

In the above example,

- <b style="color: Chartreuse;">Recursive Function:</b> `nSum()` is the Recursive Function
- <b style="color: Chartreuse;">Recursive Case:</b> The expression, `int res = n + nSum(n – 1)` is the Recursive Case.
- <b style="color: Chartreuse;">Base Condition:</b> The base condition is `if (n == 0) { return 0;}`

```
res = 5 + nSum(4) = 5 + 4 + nSum(3) = 5 + 4 + 3 + nSum(2) = 5 + 4 + 3 + 2 + nSum(1) = 5 + 4 + 3 + 2 + 1 + nSum(0) = 5 + 4 + 3 + 2 + 1 + 0 = 15
```

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Memory Management in C++ Recursion</h3>

Like all other functions, the recursive function’s data is stored in the stack memory in the form of a stack frame. This stack frame is deleted once the function returns some value. In recursion,

- The function call is made before returning the value, so the stack frame for the progressive recursive calls is stored on top of existing stack frames in the stack memory.
- When the topmost function copy returns some value, its stack frame is destroyed and the control comes to the function just before that particular copy after the point where the recursive call was made for the top copy.
- The compiler maintains an instruction pointer to track where to return after the function execution.

<b style="color: LightGreen;">Stack overflow</b> is one of the most common errors associated with the recursion which occurs when a function calls itself too many times. As we know that each recursive call requires separate space in the limited stack memory. When there is a large number of recursive calls or recursion goes on infinite times, this stack memory may get exhausted and may not be able to store more data leading to programs’ termination.

</div>

<!-- <div style="font-size: 17px;background: black;padding: 2rem;"> -->
<!-- <div style="background: DarkRed;padding: 0.3rem 0.8rem;"> [HIGHLIGHT] -->
<!-- <h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;"> [SUBHEADING] -->
<!-- <b style="color: Chartreuse;"> [NOTE] -->
<!-- <b style="color:red;"> [NOTE-2] -->
<!-- <span style="color: Cyan;"> [IMP] -></span> -->
<!-- <b style="color: Salmon;"> [POINT] -->
<!-- <div style="border: 1px solid yellow; padding: 10px;"> [BORDER] -->
