# 4.კომენტარები კოდის ფორმატირება წანაცვლები

კომენტარები ემსახურება კოდის წაკითხვადობას, ხშირად არის კოდის რომელიმე ნაწილი
რომელიც ძნელია გავიგოთ რას შვება, განსაკუთრებით თუ ჩვენი დაწერილი არ არის.
ამისთვის არსებობს კომენტარები, კომპილერი კომენტარებს ყურადღებას არ 
აქცევს და კოდად არ აღიქვავს. 
უმეტესობა პროგრამირების ენაში არსებობს ორი ტიპისკომენტარი:

- ერთ ხაზიანი კომენტარი
```cpp
int main() {
    int num = 15;
    // std::cout << num << std::endl;
}
```

- ბლოკის კომენტარი
```cpp
int main() {
    int num = 15;
    int num2 = 20;
    /*
        std::cout << num << std::endl;
        std::cout << num2 << std::endl;
    */

}
```