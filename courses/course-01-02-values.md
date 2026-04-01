## Passing by value

```cpp
// 2 variables + 1 return value
int add(int x, int y) // pass by value
{
  return x + y;
}

// 2 variables + 1 return value
mesh add(mesh a, mesh b) // pass by value
{
  return mesh(...); // create a new mesh
}
```

When passing by value:

* the program copies each input value into a local variable;
* the program runs the function, using these local variables;
* the program sends back the return value to the caller (another copy); <span style="color:blue;">*(sometimes, the compiler can skip that copy)*</span>

This is not a problem at all when using <span style="color:green;">**simple types**</span> (integers, booleans, etc...), but it can create performance (execution time, memory usage) when using more <span style="color:red;">**complex types**</span> (here a mesh).
