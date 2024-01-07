# 19. `<algorithm>` და `<numeric>` ბიბლიოთეკის რამდენიმე ალგორითმი. მათი აღწერა და გამოყენების მაგალითები.

### `<algorithm>` ბიბლიოთეკის ალგორითმები

1. `std::sort`
**აღწერა**: ალაგებს ელემენტებს ზრდადობის მიხედვით
**გამოყენება**:
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec = { 4, 123, 321,454, 12, 56 };

    std::sort(vec.begin(), vec.end());

    for(int num : vec) {
        std::cout << num << " ";
    }
    std::cout << std::endl;
}
```

2. `std::find`
**აღწერა**: პოულობს მნიშვნელობის პირველ არსებულ შემთხვევას მოცემულ დიაპაზონში 
და აბრუნებს მის მისამართს მეხსიერებაში.
**გამოყენება**:
```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> numbers = {5, 2, 8, 1, 7};
    auto it = std::find(numbers.begin(), numbers.end(), 8);

    if (it != numbers.end()) {
        std::cout << "Found: " << *it << std::endl;
    } else {
        std::cout << "Not found." << std::endl;
    }
}
```

3. `std::count`
**აღწერა**: ითვლის რამდენჯერ შეხვდება მნიშვნელობა მოცემულ დიაპაზონში და აბრუნებს
შედეგს.
**გამოყენება**:
```cpp
#include <algorithm>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> numbers = {5, 2, 8, 1, 7, 8, 8};
    
    int result = std::count(numbers.begin(), numbers.end(), 8);
    
    std::cout << "Count of 8s: " << result << std::endl;
}
```

### `<numeric>` ბიბლიოთეკის ალგორითმები

1. `std::accumulate`
**აღწერა**: აბრუნებს მოცემულ დიაპაზონში მყოფი ელემენტების ჯამს
**გამოყენება**:
```cpp
#include <numeric>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> numbers = {5, 2, 8, 1, 7, 8, 8};
    
    // ბოლო პარამეტრი, 0, არის საწყისი წერტილი, ანუ რა რიცხვს დაემატება სხვა რიცხვები
    int sum = std::accumulate(numbers.begin(), numbers.end(), 0);
    
    std::cout << "Sum of numbers: " << sum << std::endl;
}
```

2. `std::iota`
**აღწერა**: წერს ვექტორში საწყისი წერტილიდან ზრდადი რიცხვებით
**გამოყენება**:
```cpp
#include <numeric>
#include <vector>
#include <iostream>

int main() {
    std::vector<int> numbers(5);
    std::iota(numbers.begin(), numbers.end(), 1);
    
    // დაბეჭდავს 1, 2, 3, 4, 5  - ს
    for(int num : numbers) {
        std::cout << num << std::endl; 
    }
    
}
```
