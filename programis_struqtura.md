# 1. პროგრამის სტრუქტურა.

პროგრამის სტრუქტურა გულისხმობს იმას თუ როგორ არიან პროგრამის სხვადასხვა
კომპონენტები განლაგებული ჩვენს კოდში, კარგი სტრუქტურა პროგრამაში კრიტიკულია
მისი წაკითხვადობის, შენახვისთვის და ადვილად განახლებისთვის.
კომპონენტები როგორიცაა:

- import/include:
```cpp
#include<iostream>
#include<string>
```

- სხვა პრეპროცესორის დირექტივები:
```cpp
#pragma once
#define MAX 500
```

- კომენტარები:
```cpp
// ერთხაზიანი კომენტარი

/* მრავალხაზიანი/ბლოკის კომენტარი */
```

- ფუნქციების განცხადება და განმარტება:
```cpp
int multiply(const int& x, const int& y);
//....
int multiply(const int& x, const int& y) {
    return x * y;
}
```

- ცვლადების განცხადება და განმარტება(ინიციალიზება):
```cpp
int num;
num = multiply(4, 5);
```

- პროგრამის მიმართულების კონტროლის სტრუქტურები:
```cpp
if ( num % 2 == 0 ) {
    std::cout << "It's Even!" << std::endl;
} 
else {
    std::cout << "It's Odd" << std::endl;
}
```

- მთავარი ფუნქცია, კოდის შესავალი წერტილი:
```cpp
int main() {
    // კოდი
}
```