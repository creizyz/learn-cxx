## Passing by value

```cpp
// 2 input values + 1 return value
int add(int x, int y) // pass by value
{
  return x + y;
}

// 2 input values + 1 return value
mesh add(mesh a, mesh b) // pass by value
{
  return mesh(...); // create a new mesh
}
```

When passing by value:

* the program copies each input value into a local variable;
* the program runs the function, using these local variables;
* the program sends back the return value to the caller (another copy). <span style="color:blue;">_(sometimes, the compiler can skip that copy)_</span>

This is not a problem at all when using <span style="color:green;">**simple types**</span> (integers, booleans, etc...), but it can create performance (execution time, memory usage) when using more <span style="color:red;">**complex types**</span> (here a mesh).

## Passing by reference

```cpp
// 2 input references + 1 return value
mesh add(const mesh & a, const mesh & b) // pass by reference
{
  return mesh(...); // create a new mesh
}

// 1 input references + 1 in/out reference
void add_into(mesh & a, const mesh & b) // pass by reference
{
  a = mesh(...); // modify a directly
}


// 2 input references + 1 output reference
void add_into(const mesh & a, const mesh & b, mesh & c) // pass by reference
{
  c = mesh(...); // modify c
}
```

Instead of passing by value, we can pass by reference (**&** and **const &**) to reduce the performance impact.

When passing by reference:

* the program copies each **reference** into a local variable; <span style="color:blue;">_(only an address to the data)_</span>
* the program runs the function, accessing to the data via these references;
* the program sends back the return value to the caller (single copy now).

## Const or not const

The **```const``` qualifier** can be used to express if you want to access some data:

* in read only mode (const &)
* in read + write mode (&)

It's always better to declare explicitely when a reference is const or not, as it can help understand what is happening, and can reduce the risk of bugs.
