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

* Réponse : 
Dans un autre scope (body) donc mask précèdent x tant qu'elle est vivante dans le corps

```cpp
20
10
```

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
* Réponse : 
score n'est pas definie dans le scope de main (score est créée et n'existe que dans le scope de if (true))
```cpp
#include <iostream>

int main() {
    int score = 42;
    std::cout << score << "\n";
}
```



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

* Réponse :
Le programmer veut qu'une fonction créer une variable dans son corps

Et affiche cette variable .
n est créé dans le corps d'une fonction, qui n'est pas atteignable par main

```cpp
int getNumber() {
    int n = 7;
    return
}

int main() {

    int n = getNumber()
    std::cout << n << "\n";
}
```

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

Réponse :
Boucle avec variable du même nom peut prêter à confusion
```cpp
0
1
2
5
```

