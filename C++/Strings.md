<div style="font-size: 17px;background: black;padding: 2rem;">

C++ strings are sequences of characters stored in a char array. Strings are used to store words and text. They are also used to store data, such as numbers and other types of information. Strings in C++ can be defined either using the `std::string` class or the `C-style character arrays`.

<h4 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">C Style Strings</h4>

These strings are stored as the plain old array of characters terminated by a `null character '\0'`. They are the type of strings that C++ inherited from C language.

```c
char e[] = "abc";
char e1[] = {'a', 'b', 'c'};
char * c = "abc"
```

<h4 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">std::string Class</h4>

These are the new types of strings that are introduced in C++ as std::string class defined inside `<string>` header file. This provides many advantages over conventional C-style strings such as dynamic size, member functions, etc.

```c++
string s1 = "abc";
string s2("abc");
string s3(5, 'a'); // s3 = "aaaaa"
```

<h4 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Key Features</h4>

- **Automatic Memory Management:** `std::string` automatically manages the memory needed to store the string's characters, including resizing as needed.
- **Ease of Use:** Provides a wide range of member functions to manipulate strings easily.
- **Safety:** Offers bounds checking in some member functions to prevent buffer overflows.

<h2 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;">Functions</h2>

- <b style="color: Chartreuse;">length()</b> / <b style="color: Chartreuse;">size()</b>: Returns length of the string.
- <b style="color: Chartreuse;">[]</b> / <b style="color: Chartreuse;">at()</b>: Access individual characters using index.
- <b style="color: Chartreuse;">+ <i style="color: hotpink; font-weight: normal;">operator</i></b>: Used to concatenate 2 strings. <b style="color:red;">Can't use other data types while appending. Use <span style="color: orange;">to_string</span> function to change them to string first.</b>
- <b style="color: Chartreuse;">>, >=, <, <=, == <i style="color: hotpink; font-weight: normal;">operators</i></b>: Operators used to compare strings lexicographically.
- <b style="color: Chartreuse;">substr</b>: Returns substring. It takes 2 parameters - starting index of first character to be copied and length of required substring. If we don't pass 2nd arg, it takes entire length of string from given index.
- <b style="color: Chartreuse;">find</b>: Used to find the first occurrence of a sub-string in the specified string being called upon. It returns the index of the first occurrence of the substring in the string from the given starting position. The default value of starting position is `0`. `string::npos` is returned if the specified substring is not found. `string::npos` is a constant static member value of string which represents the largest possible value for the type `size_t`.
- <b style="color: Chartreuse;">replace()</b>: Used to modify a part of the string. It takes first index/iterator, length of substring to be replaced and string that is to be inserted in the range.
- <b style="color: Chartreuse;">insert()</b>: Adds a substring at a specified position. Takes 2 args - index at which insertion needs to happen and string which needs to be inserted.
- <b style="color: Chartreuse;">erase()</b>: Used to remove a part of the string. It can take 0/1/2 args. With 0 args it erases entire string, with 1 arg (and that is starting index), it erases entire string after that provided index and if we give second arg (and that is the length of string we want to delete), it deletes just the given length from given index.
- To lower case characters, `transform` function from `<algorithms>` can be used.

<br>

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    string s1 = "The Dark Knight", s2 = "Dark";
    cout << s1.length() << endl; // 15
    cout << s1[0] << endl; // T
    cout << (s1 + " " + s2) << endl; // The Dark Knight Dark
    cout << (s1 == s2) << endl; // 0
    cout << (s1 > s2) << endl; // 1
    cout << s1.substr(1, 3) << endl; // he
    
    size_t found = s1.find(s2, 1);
    if (found != string::npos)
     cout << "First occurrence is " << found << endl; // First occurrence is 4
     
    s1.replace(4, 4, "White");
    cout << s1 << endl; // The White Knight
    
    s2.insert(0, "The ");
    cout << s2 << endl; // The Dark
    
    s1.erase(0, 4);
    cout << s1 << endl; // White Knight
    
    transform(s1.begin(), s1.end(), s1.begin(), [](unsigned char c){ return tolower(c); });
    cout << s1 << endl; // white knight
    
    return 0;
}
```

</div>

<!-- <div style="font-size: 17px;background: black;padding: 2rem;"> -->
<!-- <div style="background: DarkRed;padding: 0.3rem 0.8rem;"> [HIGHLIGHT] -->
<!-- <h3 style="border-bottom: 2px solid white; padding-bottom: 2px; display: inline-block;"> [SUBHEADING] -->
<!-- <b style="color: Chartreuse;"> [NOTE] -->
<!-- <b style="color:red;"> [NOTE-2] -->
<!-- <span style="color: Cyan;"> [IMP] -></span> -->
<!-- <b style="color: Salmon;"> [POINT] -->
<!-- <div style="border: 1px solid yellow; padding: 10px;"> [BORDER] -->