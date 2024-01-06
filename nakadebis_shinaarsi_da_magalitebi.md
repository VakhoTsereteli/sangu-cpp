# 2. ნაკადების შინაარსი და მაგალითები
ნაკადები C++ - ში არის მონაცემების შეტანა/გამოტანის ფუნდამენტალური სტრუქტურა 
რომელიც შენახულია \<iostream\> ბიბლიოთეკაში , ისინი გვეხმარებიან მონაცემების 
როგორც კონსოლში შეტანა/გამოტანაში(std::cout, std::cin), ასევე ფაილებშიც
\<fstream\> ბიბლიოთეკის დახმარებით (std::ifstream, std::ofstream).
მაგალითები:

- `std::ostream` კლასის წევრი `std::cout`
```cpp
#include<iostream>

int main(){
    // დაბეჭდავს "Hello World!"-ს კონსოლში
    std::cout << "Hello World!" << std::endl;
}
```

-  `std::istream` კლასის წევრი `std::cin`
```cpp
#include <iostream>

int main() {
    int input;
    std::cout << "Enter your age: ";
    // გააჩერებს პროგრამას და დაელოდება მომხმარებელს 
    std::cin >> input; // შეინახავს შემოტანილ ინფორმაციას მითითებულ ცვლადში
    std::cout << "You are " << input << " years old" << std::endl;  
}
```

### ფაილებთან სამუშაოდ

- `std::ifstream`
```cpp
#include<iostream>
#include<fstream>

int main() {
    // შევქმნით std::ifstreamis ტიპის ცვლადს
    std::ifstream file;
    file.open("data.txt");

    std::string temp;
    file >> temp; //თუ საჭიროა მრავალი მონაცემის წამოღება ფაილიდან სასურველია გამოიყენოთ ციკლი
    
    std::cout << temp;
}
```

- `std::ofstream`
```cpp
#include<iostream>
#include<fstream>

int main() {
    std::ofstream file;
    file.open("data.txt");
    
    file << multiply(4, 5) << std::endl;
}
```