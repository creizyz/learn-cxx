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

* Réponse : 
& pour réference
donc j'imagine que la nouvelle variable ref = reférence vers x
donc modifier ref c'est modifier a
```cpp
25
25
```

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
* Réponse : 
on passe la réf de n à la fnction, donc c'est ce que la fonction modifie
```cpp
6
```

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

* Réponse : 
Pour by value la fonction set à 0 une fonction temporaire propre à son scope
et elle n'est jamais réasigné à la variable d'entrée
par ref, la fonction modifie directement la valeur de la référence déclarée dans main
```cpp
8
0
```



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
* Réponse :  Changevalue assigne 10 à une variable x, mais n'est pas retournée, donc temp vaut toujours la même chose.
Tandis que changeReference assigne 200 à la référence de la variable x
```cpp
10
200
```



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

* Réponse : les variables swap a et b ne sont jamais retournées/utilisées.

```cpp
void swapNumbers(int & a, int & b) {
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

## Exercise F

```cpp
#include <iostream>

void increment(const int & x) {
    x = x + 1;
}

int main() {
    int value = 10;

    increment(value);

    std::cout << value << "\n";
}
```

**Question**: This code won't compile. Why ? Can you fix it ?

* Réponse : 
"const" protège la référence de x en écriture.
```cpp
#include <iostream>

void increment(int & x) {
    x = x + 1;
}

int main() {
    int value = 10;

    increment(value);

    std::cout << value << "\n";
}
```


