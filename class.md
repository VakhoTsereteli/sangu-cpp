# 22. მონაცემთა ახალი ტიპის შექმნა კლასის საშუალებით და განაცხადების გაკეთება კლასის ობიექტებზე. მოკლე აღწერა მაგალითებით. 

კლასები გვაძლევენ საშუალებას რომ შევქმნათ ახალი მონაცემთა ტიპი რომელშიც ჩვენ
ვწყვეტთ რა მონაცემები ინახება და ამ მონაცემებს როგორ იყენებს და ამუშავებს,
კლასი არის ჩანახაზი რის მიხედვითაც ვაგებთ ობიექტებს.

### მაგალითი
```cpp
#include <iostream>
#include <string>

class Person {
public:
    std::string name;
    std::string surname;
    int age;

    void display_info() {
        cout << "Name: " << name << ", Surname: " << ", Age: " << age 
             << std::endl;
    }

    std::string get_full_name() {
        return name + " " + surname;
    }

    int get_age() {
        return age;
    }
};

int main() {
    Person person1;
    Person person2;

    person1.name    = "John";
    person1.surname = "Doe";
    person1.age     = 25;

    person2.name    = "Jane";
    person2.surname = "Doe";
    person2.age     = 30;

    std::cout << person1.get_full_name() << std::endl;
    person1.display_info();

    std::cout << person2.get_full_name() << std::endl;
    person2.display_info();
}
```
