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

## Exercise B

```cpp
#include <iostream>

void addOne(int& x) {
    x = x + 1;
}

int main() {
    int n = 5;
    addOne(n);
    std::cout << n << "\n";
}
```

**Question**: What does this print, and why ?

## Exercise C

```cpp
#include <iostream>

void setToZeroByValue(int x) {
    x = 0;
}

void setToZeroByReference(int& x) {
    x = 0;
}

int main() {
    int a = 8;
    int b = 8;

    setToZeroByValue(a);
    setToZeroByReference(b);

    std::cout << a << "\n";
    std::cout << b << "\n";
}
```

**Question**: What does this print, and why ?

## Exercise D

```cpp
#include <iostream>

void changeValue(int x) {
    x = 100;
}

void changeReference(int& x) {
    x = 200;
}

int main() {
    int n = 10;

    {
        int temp = n;
        changeValue(temp);
        std::cout << temp << "\n";
    }

    changeReference(n);
    std::cout << n << "\n";
}
```

**Question**: What does this print, and why ?

## Exercise E

```cpp
#include <iostream>

void swapNumbers(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
}

int main() {
    int x = 3;
    int y = 7;

    swapNumbers(x, y);

    std::cout << x << " " << y << "\n";
}
```

**Question**: This code tries to swap two numbers. Why does it fail ? Fix it.
