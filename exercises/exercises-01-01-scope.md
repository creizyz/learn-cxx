## Exercise A

```cpp
#include <iostream>

int main() {
    int x = 10;

    {
        int x = 20;
        std::cout << x << "\n";
    }

    std::cout << x << "\n";
}
```

**Question**: what does this program print, and why ?

## Exercise B

```cpp
#include <iostream>

int main() {
    if (true) {
        int score = 42;
    }

    std::cout << score << "\n";
}
```

**Question**: this program won't compile. Why ? How do you fix it ?

## Exercise C

```cpp
#include <iostream>

int getNumber() {
    int n = 7;
}

int main() {
    std::cout << n << "\n";
}
```

**Question**: this program won't compile. What do you think the programmer wanted this program to do ? Why won't this program compile ? How can you fix it ?

## Exercise D

```cpp
#include <iostream>

int main() {
    int count = 5;

    for (int count = 0; count < 3; count++) {
        std::cout << count << " ";
    }

    std::cout << "\n" << count << "\n";
}
```

**Question**: What does program print ? Why could shadowing be risky ?
