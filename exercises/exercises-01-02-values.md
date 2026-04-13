## Exercise A

```cpp
#include <iostream>

int main() {
    int a = 10;
    int b = a;

    b = 99;

    std::cout << a << "\n";
    std::cout << b << "\n";
}
```

**Question**: what does this print, and why ?
* Réponse : 
b prend la valeur de a
Puis b prend la valeur 99 sans être une nouvelle variable
```cpp
10 
99
```


## Exercise B

```cpp
#include <iostream>

void addOne(int x) {
    x = x + 1;
}

int main() {
    int n = 5;
    addOne(n);
    std::cout << n << "\n";
}
```

**Question**: what does this print, and why ?
* Reponse :
la valeur temporaire x de la fonction est créée maisn'est jamais utilisée/n'est pas renvoyée
donc n du scope main reste à valeur initial

```cpp
5
```

## Exercise C

```cpp
#include <iostream>

// ... add a square function

int main() {

    // ... use that square function

    std::cout << n << "\n";
    std::cout << result << "\n";
}
```

**Question**: Given a value (_n_), We would like to compute and print its square (_result_). Implement this with a function that takes an int by value, and returns its square.

* Reponse :
```cpp
int sqr(int n) {
    return n * n;
}
int main() {

    int n = 5;
    result = sqr(n)

    std::cout << n << "\n";
    std::cout << result << "\n";
}
```

