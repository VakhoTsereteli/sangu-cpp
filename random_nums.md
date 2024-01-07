# 20. შემთხვევითი სიდიდეები და შემთხვევითი რიცხვების განაწილება. გამოყენების მაგალითები.

შემთხვევითი სიდიდეების, ანუ შემთხვევითი რიცხვების წარმოსაქმნელად ვიყენებთ `random` ბიბლიოთეკას, რომელიც გვეხმარება C++_ში შემთხვევითობის პრინციპით წარმოვქმნათ  რიცხვები.

### მაგალითი:

```cpp
#include  <iostream>
#include  <random>
int  main(){

std::default_random_engine dre(std::random_device{}());

std::uniform_int_distribution<int>  random_int_num(1, 10);
std::uniform_real_distribution<double>  random_real_num(1, 10);

std::cout <<  "Random Int Num: "  <<  random_int_num(dre) <<  std::endl;
std::cout <<  "Random Real Num: "  <<  random_real_num(dre) <<  std::endl;

}
}
```
`default_random_engine` არის შემთხვევითი რიცხვების ძრავის კლასი, რომელიც ქმნის ფსევდო შემთხვევით რიცხვებს.

`random_device` არის ერთნაირად განაწილებული მთელი რიცხვების შემთხვევითი რიცხვების გენერატორი, რომელიც აგენერირებს შემთხვევით რიცხვებს.


`uniform_int_distribution<int>_ისა` და `uniform_real_distribution<double>_ის` გამოყენებით ჩვენ განვსაზღვრავთ როგორი შემთხვევითი რიცხვების დაგენერირება გვიდა - მთელი თუ ნამდვილი.
მათ კი პარამეტრებად გადაეცემათ ქვედა და ზედა ზღვარი - ანუ რა რიცხვებს შორის უნდა დააგენერიროს შემთხვევითი რიცხვები.


