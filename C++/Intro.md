<div style="font-size: 17px;background: black;padding: 2rem;">

C++ is a high-level (can be said mid-level), general-purpose programming language designed for system and application programming. It was developed by Bjarne Stroustrup at Bell Labs in 1983 as an extension of the C programming language. The name of C++ signifies the evolutionary nature of the changes from C. “++” is the C increment operator. C++ is an object-oriented, multi-paradigm language that supports procedural, functional, and generic programming styles. 

One of the key features of C++ is its ability to support low-level, system-level programming, i.e. <span style="color: Cyan;">it provides direct access to hardware resources and allows low-level manipulation of memory (through a feature specifically provided by C/C++ called pointers)</span> making it suitable for developing operating systems, device drivers, and other system software. At the same time, C++ also provides a rich set of libraries and features for high-level application programming, making it a popular choice for developing desktop applications, video games, and other complex applications. 

C++ programs excel in execution speed. Since, it is a <span style="color: Cyan;">compiled language</span>, and also hugely procedural, it has faster execution times and improved performance compared to <span style="color: Cyan;">interpreted languages</span> like Python Newer languages have extra in-built default features such as garbage-collection, dynamic typing etc. which slow the execution of the program overall. Since there is no additional processing overhead like this in C++, it is blazing fast.

C++ is a <span style="color: Cyan;">mid-level</span> language as we can do both systems-programming (drivers, kernels, networking etc.) and build large-scale user applications (Media Players, Photoshop, Game Engines etc.). Binary code/Machine language is low-level, C/C++ and Assembly language are mid-level and Java, Python, Cobol, etc. are high level languages.

A C++ executable is not platform-independent (compiled programs on Linux won’t run on Windows), however they are machine independent i.e. it is not tied to any hardware or processor. If the compiler compiles the program in the system, it will be able to run no matter what the hardware is.

C++ has a <span style="color: Cyan;">strong type system</span>, which means that variables have a specific type and that type must be respected in all operations performed on that variable.

C++ has <span style="color: Cyan;">STL (Standard Template Library)</span> which provides a wide range of algorithms and data structures for working with data, making it easier to write efficient and effective code.

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Applications of C++:</h3>

- <b style="color: Salmon;">System Software:</b> C++ is widely used for developing system software such as operating systems, device drivers, and embedded firmware due to its low-level capabilities and efficiency.

- <b style="color: Salmon;">Game Development:</b> Many game engines and game development frameworks, such as Unreal Engine and Unity, are built using C++. Its performance and control over hardware make it well-suited for developing high-performance games.

- <b style="color: Salmon;">Applications with Graphical User Interfaces (GUI):</b> C++ is commonly used for developing applications with graphical user interfaces, including desktop applications, software tools, and utilities. Frameworks like Qt provide extensive support for GUI development in C++.

- <b style="color: Salmon;">Financial and Trading Systems:</b> C++ is used extensively in developing financial and trading systems due to its performance, reliability, and the need for low-latency processing.

- <b style="color: Salmon;">Operating Systems Development:</b> C++ is used in the development of operating systems and system utilities due to its ability to directly access hardware resources and its efficiency in system-level programming.

- <b style="color: Salmon;">Databases and Search Engines:</b> C++ is used in the development of databases, search engines, and other high-performance data processing systems where speed and efficiency are critical.

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">First C++ program</h3>

```c++
// C++ program to display "Hello World"
 
// Header file for input output functions
#include <iostream>
using namespace std;
 
// Main() function: where the execution of
// program begins
int main()
{
    // Prints hello world
    cout << "Hello World";
 
    return 0;
}
```

1. <span style="color: Orange;">// C++ program to display “Hello World”</span>: This line is a comment line. A comment is used to display additional information about the program. A comment does not contain any programming logic. When a comment is encountered by a compiler, the compiler simply skips that line of code. Any line beginning with `//` without quotes OR in between `/*…*/` in C++ is a comment. 

2. <span style="color: Orange;">#include</span>: This is a preprocessor directive. The #include directive tells the compiler to include the content of a file in the source code. For example, `#include <iostream>` tells the compiler to include the standard `iostream` file which contains declarations of all the standard input/output library functions. 

3. <span style="color: Orange;">using namespace std</span>: This is used to import the entity of the `std` namespace into the current namespace of the program. The statement using namespace `std` is generally considered a bad practice. When we import a namespace we are essentially pulling all type definitions into the current scope. The `std` namespace is huge. The alternative to this statement is to specify the namespace to which the identifier belongs using the scope `operator(::)` each time we declare a type. For example, `std::cout`.

4. <span style="color: Orange;">int main() {}</span>: A function is a group of statements that are designed to perform a specific task. The `main()` function is the entry point of every C++ program, no matter where the function is located in the program. The opening braces `{` indicates the beginning of the main function and the closing braces `}` indicates the ending of the main function. 

5. <span style="color: Orange;">cout<<“Hello World”;</span>: `std::cout` is an instance of the `std::ostream` class, that is used to display output on the screen. Everything followed by the character `<<` in double quotes `” ”` is displayed on the output device. The semi-colon character at the end of the statement is used to indicate that the statement is ending there. Click to know More on Input/Output.

6. <span style="color: Orange;">return 0</span>: This statement is used to return a value from a function and indicates the finishing of a function. This statement is basically used in functions to return the results of the operations performed by a function.

7. <span style="color: Orange;">Indentation</span>: As you can see the `cout` and the return statement have been indented or moved to the right side. This is done to make the code more readable. We must always use indentations and comments to make the code more readable. 

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Tokens</h3>

In C++, tokens are the smallest units of a program, much like words are the smallest units of a language. These tokens are the building blocks of C++ code and are categorized into several types:

1. <b style="color: Salmon;">Keywords:</b> Keywords are reserved words that have predefined meanings in the C++ language. Examples include `int`, `double`, `if`, `else`, `class`, `return`, etc.

2. <b style="color: Salmon;">Identifiers:</b> Identifiers are names given to various program elements such as variables, functions, classes, etc. They consist of letters, digits, and underscores, with the first character being a letter or an underscore. 
    - An identifier can only begin with a letter or an underscore(_). 
    - An identifier can consist of letters (A-Z or a-z), digits (0-9), and underscores (_). White spaces and Special characters can not be used as the name of an identifier.
    - Identifier must be unique in its namespace.
    - Keywords cannot be used as an identifier because they are reserved words to do specific tasks.

3. <b style="color: Salmon;">Literals:</b> Literals are constant values that are directly used in the program. Examples include integer literals `(123, -42)`, floating-point literals `(3.14, -0.001)`, character literals `('a', 'B')`, string literals `("hello", "world")`, boolean literals `(true, false)`, and null pointer literals `(nullptr)`.

4. <b style="color: Salmon;">Operators:</b> Operators are symbols used to perform operations on operands. C++ supports a variety of operators such as arithmetic operators `(+, -, *, /, %)`, relational operators `(==, !=, <, >, <=, >=)`, logical operators `(&&, ||, !)`, assignment operators `(=, +=, -=, *=, /=)`, and many others.

5. <b style="color: Salmon;">Punctuators:</b> Punctuators are symbols used to punctuate or separate different parts of the code. Examples include braces `{}`, parentheses `()`, brackets `[]`, commas `,`, semicolons `;`, colons `:`, etc.

6. <b style="color: Salmon;">Comments:</b> Comments are not considered part of the executable code but are used for documentation purposes. C++ supports single-line comments `(//)` and multi-line comments `(/* */)`.

7. <b style="color: Salmon;">Preprocessor Directives:</b> Preprocessor directives are instructions to the preprocessor, which is a program that processes the source code before compilation. Examples include `#include`, `#define`, `#ifdef`, `#ifndef`, `#endif`, etc.

</div>

<!-- <div style="font-size: 17px;background: black;padding: 2rem;"> -->
<!-- <div style="background: DarkRed;padding: 0.3rem 0.8rem;"> [HIGHLIGHT] -->
<!-- <h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;"> [SUBHEADING] -->
<!-- <b style="color: Chartreuse;"> [NOTE] -->
<!-- <b style="color:red;"> [NOTE-2] -->
<!-- <span style="color: Cyan;"> [IMP] -></span> -->
<!-- <b style="color: Salmon;"> [POINT] -->
<!-- <div style="border: 1px solid yellow; padding: 10px;"> [BORDER] -->