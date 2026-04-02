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
