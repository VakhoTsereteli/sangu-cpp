# 14.continue შეტყობინება. რომელი შეტყობინებები იყენებს მას.შინაარსი მაგალითები.
`continue` დაასრულებს ციკლის ეხლანდელ იტერაციას და გადავა შემდეგ იტერაციაზე.
```cpp
#include <iostream>

int main() {
    int count = 0;

    while(count < 10) {
        if(count % 2 != 0) {
            continue;
        }

        std::cout << count << " ";
        count++;
    }
    std::cout << std::endl;
}
```