<div style="font-size: 17px;background: black;padding: 2rem;">

An operator is a symbol that operates on a value to perform specific mathematical or logical computations. They form the foundation of any programming language. In C++, we have built-in operators to provide the required functionality. An operator operates the operands. For example, in `int c = a + b`, ‘+’ is the addition operator. ‘a’ and ‘b’ are the operands that are being ‘added’. Operators in C++ can be classified into 6 types:

1. <b>Arithmetic Operators</b>
2. <b>Relational Operators</b>
3. <b>Logical Operators</b>
4. <b>Bitwise Operators</b>
5. <b>Assignment Operators</b>
6. <b>Ternary or Conditional Operators</b>

<br>

# 1. Arithmetic Operators

Arithmetic Operators in C++ are used to perform arithmetic or mathematical operations on the operands. For example, ‘+’ is used for addition, ‘–‘ is used for subtraction, ‘\*’ is used for multiplication, etc. In simple terms, arithmetic operators are used to perform arithmetic operations on variables and data.

C++ Arithmetic operators are of 2 types:

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">1. Binary Arithmetic Operator</h3>

- <span style="color: HotPink;">+ (Addition)</span>: Used in calculating the Addition of two operands.
- <span style="color: HotPink;">- (Subtraction)</span>: Used in calculating Subtraction of two operands.
- <span style="color: HotPink;">\* (Multiplication)</span>: Used in calculating Multiplication of two operands.
- <span style="color: HotPink;">/ (Division)</span>: Used in calculating Division of two operands.
- <span style="color: HotPink;">% (Modulus)</span>: Used in calculating Remainder after calculation of two operands. This operator should only be used with integers.

```c++
// C++ program to execute all 5 arithmetic function
 int x = 10, y = 3;
 
 // printing the sum of x and y
 cout<< "x + y = " << (x + y) << endl; // Output = 13
 
 // printing the difference of x and y
 cout << "x - y = " << (x - y) << endl; // Output = 7
 
 // printing the product of x and y
 cout << "x * y = " << (x * y) << endl; // Output = 30
 
 // printing the division of x by y
 cout << "x / y = " << (x / y) << endl; // Output = 3

 // printing the modulo of x by y
 cout << "x % y = " << (x % y) << endl; // Output = 7
```

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">2. Unary Arithmetic Operator</h3>

- <span style="color: HotPink;">++ (Increment)</span>: Increases the integer value of the variable by one. It can be used as both prefix and postfix to the operand.
- <span style="color: HotPink;">-- (Decrement)</span>: Decreases the integer value of the variable by one. It can be used as both prefix and postfix to the operand.
- <span style="color: HotPink;">+ (Unary Plus)</span>: Explicitly specifies the positive value of its operand. It doesn’t change the sign of a if it’s already positive, but it can be used for clarity in expressions.
- <span style="color: HotPink;">- (Unary Minus)</span>: If the operand is negative, this operator will make it positive and vice versa.


```c++
 int x = 5;

 // Increment Operator (++)
 cout << "Initial value of x: " << x << endl; // Initial value of x: 5
 x++; // Increment x by 1
 cout << "After x++, x is now: " << x << endl; // After x++, x is now: 6

 int a = 10;
 int b, c;

 b = ++a; // Prefix increment: first, increment a, then assign to b

 c = a++; // Postfix increment: first, assign a to c, then increment a
 
 cout << "a: " << a << ", b: " << b << ", c: " << c << endl; // a: 12, b: 11, c: 11

 int d = +a; // 12 is stored in d
 int e = -a; // -12 is stored in e
```


# 2. Relational Operators

Relational operators are used to compare two values or expressions, and based on this comparison, it returns a boolean value (either `true` or `false`) as the result. Generally `false` is represented as `0` and `true` is represented as any non-zero value (mostly `1`).

- <span style="color: HotPink;">> (Greater than)</span>: Returns true if the left operand is greater than the right operand.
- <span style="color: HotPink;">< (Less than)</span>: Returns true if the left operand is less than the right operand.
- <span style="color: HotPink;">>= (Greater than equal to)</span>: Returns true if the left operand is greater than or equal to the right operand.
- <span style="color: HotPink;"><= (Less than equal to)</span>: Returns true if the left operand is less than or equal to the right operand.
- <span style="color: HotPink;">== (Equal to)</span>: Returns true if the left operand is equal to the right operand.
- <span style="color: HotPink;">!= (Not equal to)</span>: Returns true if the left operand is not equal to the right operand.

```c++
// variables for comparison 
 int a = 10, b = 6; 
  
 cout << "a > b = " << (a > b) << endl;  // a > b = 1
 cout << "a < b = " << (a < b) << endl;  // a < b = 0
 cout << "a == b = " << (a == b) << endl; // a == b = 0
 cout << "a != b = " << (a != b) << endl; // a != b = 1
  
 return 0; 
```


# 3. Logical Operators

These are symbols that allow you to combine or modify conditions to make logical evaluations. They are used to perform logical operations on boolean values (`true` or `false`).

- <span style="color: HotPink;">&& (Logical AND operator)</span>: It is a binary operator that returns true if both of its operands are true. Otherwise, it returns false.
- <span style="color: HotPink;">< (Logical OR operator)</span>: Is a binary operator that returns true if either of its operands are true. Otherwise, it returns false.
- <span style="color: HotPink;">>= (Greater than equal to)</span>: It is a unary operator that is used to negate the value of a condition. It returns true if the condition is false, and false if the condition is true.

```c++

int x = 1, y = 0;

int a = x && y; // a -> 0
int b = x || y; // b -> 1
int c = !y; // c -> 1
int d = (x > y) && (y == 0); // d -> 1
```


# 4. Bitwise Operators

- <span style="color: HotPink;">& (Bitwise AND)</span>: It is performed between two integers. It will compare each bit on the same position and the result bit will be set(1) only and only if both corresponding bits are set(1).
- <span style="color: HotPink;">| (Bitwise OR)</span>: It is also performed between two integers. It will compare each bit on the same position and the result bit will be set(1) if any of corresponding bits are set(1).
- <span style="color: HotPink;">^ (Bitwise XOR)</span>: It is also performed between two integers. It will compare each bit on the same position and the result bit will be set(1) if both corresponding bits are different.
- <span style="color: HotPink;">~ (Bitwise NOT)</span>: It is performed on a single number. It change the current bit to it’s complement , i.e. if current bit is 0 then in result it will be 1 and if current bit is 1 then it will become 0.
- <span style="color: HotPink;"><< (Left Shift)</span>: This operator shifts the bits of Integer to left side by specific number (As mentioned) . This left shift operation is equivalent to multiplying the integer by 2 power number of positions shifted.
- <span style="color: HotPink;">>> (Right Shift)</span>: This operator shifts the bits of Integer to right side by specific number (As mentioned) . This right shift operation is equivalent to dividing the integer by 2 power number of positions shifted.

```c++
int a = 5; //  101
int b = 3; //  011

int bitwise_and = a & b; // 1

int bitwise_or = a | b; // 7

int bitwise_xor = a ^ b; // 6

int bitwise_not = ~a; // -6

int left_shift = a << 2; // 20

int right_shift = a >> 1; // 2
```


# 5. Assignment Operator

The assignment operator forms the backbone of many algorithms and computational processes by performing a simple operation like assigning a value to a variable.

Syntax:

```
variable = value;
```

The right-hand side `value` will be assigned to the `variable` on the left-hand side. The variable and the value should be of the same data type. The value can be a literal or another variable of the same data type.

Example:

```c++
int a = 10; // a ->10
int b = a;  // b -> 10
```

<h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Compound Assignment Operators</h3>

The assignment operator can be combined into a single operator with some other operators to perform a combination of two operations in one single statement. These operators are called `Compound Assignment Operators`. Example:

```c++
int x = 10;
x += 5; // This is same as x = x + 5. So, 15 is stored in x after this expression.
```

These are 10 combined assignment operators: `+=, -=, *=, /=, %=, &=, |=, ^=, <<=, >>=`


# 6. Ternary/Conditional Operator

The `ternary` or `conditional` operator `( ? : )` is the shortest form of writing conditional statements. It can be used as an inline conditional statement in place of if-else to execute some conditional code. Syntax:

```
expression ? statement_1 : statement_2;
```

- <b>expression:</b> Condition to be evaluated.
- <b>statement_1:</b> Statement that will be executed if the expression evaluates to true.
- <b>statement_2:</b> Code to be executed if the expression evaluates to false.

```c++
 int num, test = 40; 

 num = test < 10 ? 10 : test + 10;  // test -> 10

 int A = 39, B = 10, C = 23; 
  
 int maxNum = (A > B) ? ((A > C) ? A : C) : ((B > C) ? B : C); // maxNum -> 39
```

<br>

# SOME OTHER OPERAOTORS

- <span style="color: HotPink;">sizeof</span>: It is a unary compile-time operator used to determine the size of variables, data types, and constants in bytes at compile time. It can also determine the size of classes, structures, and unions. `sizeof(char)` gives 1, `sizeof(int)` gives 4, etc.

</div>

<!-- <div style="font-size: 17px;background: black;padding: 2rem;"> -->
<!-- <div style="background: DarkRed;padding: 0.3rem 0.8rem;"> [HIGHLIGHT] -->
<!-- <h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;"> [SUBHEADING] -->
<!-- <b style="color: Chartreuse;"> [NOTE] -->
<!-- <b style="color:red;"> [NOTE-2] -->
<!-- <span style="color: Cyan;"> [IMP] -></span> -->
<!-- <b style="color: Salmon;"> [POINT] -->
<!-- <div style="border: 1px solid yellow; padding: 10px;"> [BORDER] -->
