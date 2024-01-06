# 7. გამოსახულება

გამოსახულება არის ერთი ან მეტი ოპერანდის და ოპერატორის კომბინაცია რომლის
გამოთვლის შედეგად ერთ მნიშვნელობას მივიღებთ. გამოსახულებები შეიძლება იყოს
რაიმე მარტივი გამოთვლა ან ცვლადების, მუდმივების და ფუნქციების გამოძახებების
რთული კომბინაცია.


- არითმეტიკული გამოსახულებები
```cpp
int a = 5, b = 3;
int jami     = a + b;
int sxvaoba  = a - b;
int namravli = a * b;
int ganayofi = a / b;
int nashti   = a % b;
```

- შედარების გამოსახულებები
```cpp
int x = 10, y = 20;
bool tolia    = (x == y);
bool ar_toli  = (x != y);
bool metia    = (x > y);
bool naklebia = (x < y);
bool m_an_t   = (x >= y);
bool n_an_t   = (x => y);
```

- ლოგიკური გამოსახულებები
```cpp
bool piroba1 = true, piroba2 = false;
bool logikuri_da = (piroba1 && piroba2);
bool logikuri_an = (piroba1 || piroba2);
bool logikuri_ar = (!piroba1);
```

- შემოკლებული მინიჭების გამოსახულებები
```cpp
int a = 5;
a += 3; // იგივეა რაც a = a + 3;
a -= 2; // იგივეა რაც a = a - 2;
a *= 4; // იგივეა რაც a = a * 4;
a /= 5; // იგივეა რაც a = a / 5;
```

- ინკრემენტაციის და დეკტრემენტაციის გამოსახულებები
```cpp
int counter = 0;
counter++; // ერთით მომატება
counter--; // ერთით შემცირება
```

- ფუნქციის გამოძახებიანი გამოსახულებები
```cpp
int result = multiply(5, 4);
```