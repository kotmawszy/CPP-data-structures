# Basic Data Structures

## Table of content
- Linear
  - [Stack](#stack)
    - [Template arguments](#template-arguments)
    - [Functions](#functions)
    - [Usage](#usage)
  - [List](#list)
    - [Template arguments](#template-arguments-2)
    - [Functions](#functions-2)
    - [Usage](#usage-2)
  - [Vector](#vector)
  - [Template arguments](#template-arguments-3)
  - [Functions](#functions-3)
  - [Usage](#usage-3)
- Trees
  - [Binary Search Tree]()
  - [Interval Tree]()
- Other
  - [Disjoint-set]()

---

# Stack

[Documentation in separate file](Linear/Stack)

## Template arguments
`T` - Type of elements.

## Functions

### push

Return: `none`
<br>
Arguments: `T`

Pushes element with a given value on the top of a stack.

### pop

Return: `none`
<br>
Arguments: `none`

Removes element from the top of a stack.

### top

Return: `T`
<br>
Arguments: `none`

Gets value of the top element.

### size

Return: `unsigned int`
<br>
Arguments: `none`

Gets size of the stack.

### empty

Return: `bool`
<br>
Arguments: `none`

Returns whether the stack is empty.

### begin
Return: `iterator`
<br>
Arguments: `none`

Returns iterator object to the first element.

### end
Return: `iterator`
<br>
Arguments: `none`

Returns iterator object to the element past the last.

## Usage

Library include
```c++
#include "path/to/Basic-Data-Structures/include/stack"
```

Stack declaration
```c++
Stack<int> s;
```

Basic `push`, `pop` and `top` usage
```c++
s.push(4);                      // stack:  4
s.push(1);                      // stack:  1 4
s.pop();                        // stack:  4
s.push(3);                      // stack:  3 4
std::cout << s.top() << "\n";   // prints: 3
s.push(2);                      // stack:  2 3 4
std::cout << s.top() << "\n";   // prints: 2
```

Print stack using `empty`, `top` and `pop`
```c++
while(!s.empty()) {
    std::cout << s.top() << "\n";
    s.pop();
}
```

Print stack using `iterator` (recommended way)
```c++
for(Stack<int>::iterator i = s.begin(); i != s.end(); ++i) {
    std::cout << *i << "\n";
}
```

Print stack using `iterator` with `range-based for loop` and `auto` (recommended way for C++11 and higher)
```c++
for(auto i : s) {
    std::cout << i << "\n";
}
```

[Full example code](Linear/Stack/example.cpp)

---

# List

[Documentation in separate file](Linear/List)

## Template arguments
`T` - Type of elements.

## Functions

### push_front

Return: `none`
<br>
Arguments: `T`

Pushes element with a given value to the front.

### push_back

Return: `none`
<br>
Arguments: `T`

Pushes element with a given value to the back.

### pop_front

Return: `none`
<br>
Arguments: `none`

Removes element from the front.

### pop_back

Return: `none`
<br>
Arguments: `none`

Removes element from the back.

### front

Return: `T`
<br>
Arguments: `none`

Returns front element.

### back

Return: `T`
<br>
Arguments: `none`

Returns back element.

### size

Return: `unsigned int`
<br>
Arguments: `none`

Returns size of the list.

### empty

Return: `bool`
<br>
Arguments: `none`

Returns whether the list is empty.

### begin
Return: `iterator`
<br>
Arguments: `none`

Returns iterator object to the front element.

### end
Return: `iterator`
<br>
Arguments: `none`

Returns iterator object to past the back element.

## Usage

Library include
```c++
#include "path/to/Basic-Data-Structures/include/list"
```

List declaration
```c++
List<int> l;
```

Basic `push_front`, `push_back`, `pop_front`, `pop_back`, `front` and `back` usage
```c++
l.push_front(3); // list: 3
l.push_front(2); // list: 2 3
l.push_back(4);  // list: 2 3 4
l.push_back(5);  // list: 2 3 4 5
l.push_front(1); // list: 1 2 3 4 5
std::cout << l.front() << "\n"; // prints 1
std::cout << l.back() << "\n";  // prints 5
l.pop_front(); // list: 2 3 4 5
l.pop_back();  // list: 2 3 4
l.pop_front(); // list: 3 4
std::cout << l.front() << "\n"; // prints 3
std::cout << l.back() << "\n";  // prints 4
```

Print list using `empty`, `front` and `pop_front`
```c++
while(!l.empty()) {
    std::cout << l.front() << "\n";
    l.pop_front();
}
```

Print stack using `iterator` (recommended way)
```c++
for(List<int>::iterator i = l.begin(); i != l.end(); ++i) {
    std::cout << *i << "\n";
}
```

Print list using `iterator` with `range-based for loop` and `auto` (recommended way for C++11 and higher)
```c++
for(auto i : l) {
    std::cout << i << "\n";
}
```

[Full example code](Linear/List/example.cpp)

---

# Vector

[Documentation in separate file](Linear/Vector)

## Template arguments
`T` - Type of elements.

## Functions

### push_back
Return: `none`
<br>
Arguments: `T`

Adds an element to the back.

### operator[]
Return: `T`
<br>
Arguments: `unsigned int`

Access specified element.

### size
Return: `unsigned int`
<br>
Arguments: `none`

Returns the number of elements.

### empty
Return: `bool`
<br>
Arguments: `none`

Returns whether the vector is empty.

### begin
Return: `iterator`
<br>
Arguments: `none`

Returns an iterator to the begining.

### end
Return: `iterator`
<br>
Arguments: `none`

Returns an iterator to the end.

## Usage

Library include
```c++
#include "path/to/Basic-Data-Structures/include/vector"
```

Vector declaration
```c++
Vector<int> v;
```

Basic `push_back` and `operator[]` usage
```c++
v.push_back(3);  // vector: 3
v.push_back(7);  // vector: 3 7
v.push_back(-2); // vector: 3 7 -2
v[1] = 4;        // vector: 3 4 -2
std::cout << v[2] << "\n"; // prints -2
std::cout << v[1] << "\n"; // prints 4
```

Print vector using `size` and `operator[]`
```c++
for(int i = 0; i < v.size(); i++) {
    std::cout << v[i] << "\n";
}
```

Print vector using `iterator` with `range-based for loop` and `auto` (C++11)
```c++
for(auto i : v) {
    std::cout << i << "\n";
}
```

[Full example code](Linear/Vector/example.cpp)
