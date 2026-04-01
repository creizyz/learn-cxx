## Function signature and body

```cpp
int add(int x, int y) // function signature
{ // function body
    return x + y;
}
```

## Function declaration

```cpp
int add(int x, int y);
```

What it does:

* Informs the compiler about the function name
* Specifies return type and parameters
* Does not provide implementation

Why you need it:

* Allows you to use the function before its definition appears
* Common in header files

## Function definition

```cpp
int add(int x, int y)
{
    return x + y;
}
```

What it does:

* Tells the compiler the function exists
* Shows how it works
* Allocates the actual code in memory

Key point:

* A definition both **declares** and **implements** the function.

