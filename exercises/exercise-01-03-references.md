## Exercise A

```cpp
#include <iostream>

int main() {
    int x = 10;
    int& ref = x;

    ref = 25;

    std::cout << x << "\n";
    std::cout << ref << "\n";
}
```

**Question**: What does this print, and why ?
