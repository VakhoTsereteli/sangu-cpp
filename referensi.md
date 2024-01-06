# 6. რეფერენსი

რეფერენსი არის იგივე ცვლადისთვის ალტერნატიული სახლელის შექმნა, როცა რეფერენსი
არის ინიციალიზირებული ნებისმიერი ცვლილება რეფერენსზე აისახება ორიგინალ ცვლადზეც
და პირიქით.

```cpp
#include <iostream>

int main() {
    int num = 10;
    
    int& ricxvi = num;
    
    ricxvi++;
    
    // დაბეჭდავს 11-ს
    std::cout << num << std::endl;

}
```

რეფერენსების მთავარი ძალა მდგომარეობს იმაში თუ როგორ ვიყენებთ მათ ფუნქციებში
პარამეტრების გადასაცემად.

განვიხილოთ ესეთი მაგალითი:

```cpp
#include <iostream>

void modify(int x) {
    x++;
}

int main() {
    int num = 10;
    modify(num);
    // დაბეჭდავს 10-ს
    std::cout << num << std::endl;
}

```
მაგრამ თუ ფუნქციას ჩვენ პარამეტრს რეფერენსით გადავცემთ:

```cpp
#include <iostream>

void modify(int& x) {
    x++;
}

int main() {
    int num = 10;
    modify(num);
    // დაბეჭდავს 11-ს
    std::cout << num << std::endl;
}

```