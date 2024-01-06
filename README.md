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

- ცვლადების განცხადება და განმარტება:
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
    file >> temp;
    
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

# 3.სტილი კარგი სტილის ზოგიერთი რჩევა(რეკომენდაცია).

კარგი სტილი გულისხმობს სხვადასხვა გზებით კოდის დაფორმატებას და სტრუქტურიზაციას.
ეს აუცილებელია კოდის წაკითხვადობის, ხარისხიანი კოლაბორაციის და განახლების 
სიადვილისთვის.მრავალი ერთმანეთისგან განსხვავებული სტილი არსებობს რომელიც
გუნდებსა და პროგრამირების ენებზეა დამოკიდებული, მთავარია ერთმანეთში არ ავურიოთ
ისინი.
მაგალითები სხვადასხვა სტილის:

- ინდენტაცია
```cpp
int main() {
        // 4 space ინდენტაცია
        std::cout << "Hello World!" << std::endl;
}
```
```cpp
int main() {
    // 4 space ინდენტაცია
    std::cout << "Hello World!" << std::endl;
}
```
```cpp
int main() {
  // 2 space ინდენტაცია
  std::cout << "Hello World!" << std::endl;
}
```

- ბრეკეტების ადგილი
```cpp
int main() {

}
```
```cpp
int main()
{
}
```
```cpp
// მოკლე ფუნქციის შემთხვევაში ზოგი პროგრამისტი ერთ ხაზზეც წერს მათ
int main() {}
```

- სახელების დარქმევა
```cpp
int snake_case;
int camelCase;
int PascalCase;
int kebab-case;

// მუდმივი ცვლადების შემთხვევაში ზოგი პროგრამისტი ასე წერს
const int MAX_LIMIT;
```

- პროექტში ფაილების კარგი ორგანიზაცია

# კომენტარები კოდის ფორმატირება წანაცვლები

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

# 5.ცვლადი, მისი მისამართი და სიგრძე.სახელის დარქმევის წესები. ინიციალიზების გზები.

ყველა ცვლადი ინახავს სხვადასხვა მონაცემს ან მონაცემებს, მონაცემი შეიძლება იყოს
სხვადასხვა ტიპის რაც წყვეტს მის ზომას ბაიტებში და შესაბამისად მის
სიგრძეს მეხსიერებაში.

ცვლადის ტიპები და მათი ზომები ბაიტებში:

| ტიპი   | მნიშვნელობა 			   | ზომა	  |
|--------|-------------------------|----------|
| int    | მთელი რიცხვი            |	4     |
| float  | ათწილადი    			   |    4     |
| double | ორმაგი სიზუსტის ათწილადი|    8     |
| char   | სიმბოლო                 |    1     |
| bool   | ბულეანი                 |    1     |


სახელს როცა ვარქმევთ ცვლადებს უნდა გავითვალისწინოთ რო მისი სახელი კარგად უნდა
აღწერდეს მის დანიშნულებას კოდში. სახელები როგორიც x, y და n არაფრის მანიშნებელია
მაგრამ თუ მაგალითად სახელი იქნება person\_age, max\_limit ან first_name უკვე 
აშკარაა რას ინახავენ ეს ცვლადები.

ცვლადების ინიციალიზაციის სხვადასხვა გზა არსებობს, ყველა სიტუაციურია, მაგალითად:
```cpp
int main() {
    // დეკლარაციის დროს ინიციალიზაცია
    int a = 4;
    
    // დეკლარაცია და მოგვიანებით ინიციალიზაცია
    int b;
    b = 10;
    
    // Default ინიციალიზაცია
    int c{};
}
```

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

# ნულოვანი ეფექტი

ნულოვანი ეფექტი არის როდესაც პროგრამაში გვიწერია გამოსახულება რომელიც რაიმე
შედეგს აბრუნებს და ჩვენ ამ შედეგს არ ვიყენებთ და არც ვინახავთ.
მაგალითად:

```cpp
#include <iostream>

int square(const int& x) {
    return x * x;
}

int main() {
    square(5); // შედეგი იკარგება
}
```

# 9.მონაცემთა რამდენიმე ტიპი, რომლის ამოცნობა შეუძლია კომპილერს auto -თი.

- პრიმიტიული ტიპები
```cpp
auto x  = 12;   // int
auto pi = 3.14; // double
auto ch = 'A';  // char
```

- რეფერენსები
```cpp
int val = 5;
auto& ref = val; // int&
```

- პოინტერები
```cpp
int val2 = 10;
auto p = &val2; // int*
```

- მასივები
```cpp
int arr[] = { 1, 2, 3, 4, 5 };
auto arr_copy = arr; // int[5]
```

- სტანდარტული კონტეინერები
```cpp
std::vector<int> vec;
auto vec_copy = vec; // std::vector<int>
```
და კიდე ბევრი სხვადასხვა ტიპი, `auto`-ს შეუძლია ტიპის დედუქცია იმის მიხედვით
თუ რას ვანიჭებთ მას.


# 10.შემოკლებული ოპერატორები. გვერდით ეფექტები.

არსებობს რამოდენიმე შემოკლებული არითმეტიკული ოპერატორი:
```cpp
int a = 5;
a += 3; // იგივეა რაც a = a + 3;
a -= 2; // იგივეა რაც a = a - 2;
a *= 4; // იგივეა რაც a = a * 4;
a /= 5; // იგივეა რაც a = a / 5;
```

მათ დაუკვირვებლად გამოყენებას შეიძლება რამოდენიმე გვერდითი ეფექტი მოყვეს,
მაგალითად, არ უნდა დაგვავიწყდეს რომ შემოკლებული არითმეტიკული ოპერატორები
ასრულებენ როგორც გამოთვლას, ასევე მინიჭებას, ანუ ორიგინალი ცვლადის ცვლილება
ხდება.

ასევე არის სიტუაციები სადაც მათი მოხერხებულობა აზიანებს კოდის წაკითხვადობას.
მაგალითად:
```cpp
x += y * (z / 2) - (w % 3);
```

ასევე უნდა გვახსოვდეს ინკრემენტაციის და დეკრემენტაციის ოპერატორები როგორ
მუშაობენ, მათმა არასწორმა გამოყენებამ შეიძლება არასწორი შედეგები გამოიწვიონ

```cpp
int val = 5;

std::cout << val++; // დაბეჭდავს 5-ს და მერე მოუმატებს ერთს val-ს
std::cout << ++val  // მოუმატებს ერთს val-ს და მერე დაბეჭდავს 6-ს 
```

> არ დაგვავიწყდეს რომ `val++` არის იგივე რაც `val += 1` რომელიც იგივეა რაც
> `val = val + 1` ანუ ორიგინალი ცვლადის ცვლილება ხდება

# 11.განმეროების while შეტობინება: შინაარსი და მაგალითები. შეტყობინებები, რომლებსაც ის იყენებს განმეორების სხვადასხვა ვარიანტის ორგანიზებისთვის.

`while` ციკლი არის განაცხადი რომელიც კოდის ბლოკს ზედიზედ რამოდენიმეჯერ 
შეასრულებს. იგი ყოველ იტერაციაზე ამოწმებს პირობას და თუ იგი ჭეშმარიტია,
აგრძელებს მუშაობას, თუარადა ჩერდება და პროგრამა გადადის შემდეგ განაცხადზე.
ეს ძალიან გამოსადეგია რადგან პროგრამისტს აღარ უწევს ერთი და იგივე კოდის დაწერა
100-ჯერ ან 200-ჯერ და სიტუაციებს სადაც რაოდენობა რამდენჯერაც ჩვენ გვინდა რომ
კოდის ბლოკი გავუშვათ არის ცვლადი, თუ `while`-ის გარეშე იყო ფაქტიურად შეუძლებელი,
მისი დახმარებით ძალიან ადვილი და მოსახერხებელია.

- `while`-ის სინტაქსი
```cpp
while(პირობა) {
    // კოდი 
}
```

- გამოყენების მაგალითი:
```cpp
#include <iostream>

int main() {
    int count = 0;

    while(count < 10) {
        std::cout << count << " ";
        count++;
    }
    std::cout << std::endl;
}
```

`while`-ში ასევე შეგვიძლია ორი სპეციალური განაცხადი, `break` და `continue`.
`break` მთლიანად დაასრულებს ციკლს და პროგრამა გადავა შემდეგ ციკლის შემდეგ
მყოფ განაცხადზე.
`continue` დაასრულებს ციკლის ეხლანდელ იტერაციას და გადავა შემდეგ იტერაციაზე.

გამოყენების მაგალითები:

- `break`
```cpp
#include <iostream>

int main() {
    int count = 0;

    while(count < 10) {
        if(count == 6) {
            break;
        }

        std::cout << count << " ";
        count++;
    }
    std::cout << std::endl;
}
```
ეს პროგრამა დაბეჭდავს რიცხვებს 5-ის ჩათვლით რის შემდეგაც მივალთ `break`
განაცხადთან რომელიც ჩვენ ციკლს დაასრულებს, რის შემდეგაც პროგრამა გადავა
შემდეგ განაცხადზე რომელიც არის ახალი ხაზის დაბეჭდვა და დაასრულებს მუშაობას
მისი შესრულების მერე.

- `continue`
```cpp
#include <iostream>

int main() {
    int count = 0;

    while(count < 10) {
        if(count % 2 != 0) {
            break;
        }

        std::cout << count << " ";
        count++;
    }
    std::cout << std::endl;
}
```
ეს პროგრამა დაბეჭდავს ყველა ლუწ რიცხვს 10-ამდე

# 12.განმეროების for შეტყობინება და დიაპაზონიანი for შეტყობინება: შინაარსი და მაგალითები. შეტყობინებები, რომლებსაც ისინი იყენებენ განმეორების სხვადასხვა ვარიანტის ორგანიზებისთვის.

`for` ციკლი მუშაობს ზუსტად ისე როგორც `while` ციკლი, მაგრამ განსხვავება ისაა
რომ `for` ციკლში გვაქ დამატებითი ფუნქციონალი რომელიც ბევრად უფრო მოსახეხებელია
ისეთ სიტუაციებში სადაც რაიმე კონკრეტულ \"მანძილზე\" იტერაცია გვინდა.

- `for` - ციკლის სინტაქსი:
```cpp
for (ინიციალიზაცია; პირობა; იტერაცია) {
    // კოდი
}
```

- გამოყენების მაგალითი
```cpp
#include <iostream>

int main() {
    std::vector<int> vec = { 1, 2, 3, 4, 5, 6, 7, 8, 9 };

    for (int i = 0; i < vec.size(); i++) {
        std::cout << vec[i] << " ";
    }
    std::cout << std::endl;
}
```
ეს პროგრამა დაბეჭდავს ყველა ვექტორში მყოფ ელემენტს

`break` და `continue` განაცხადებს ზუსტად იგივე ეფექტი აქვთ `for` ციკლში:

- `break`
```cpp
#include <iostream>

int main() {
    for(int i = 0; i < 10; i++) {
        if(i == 6) {
            break;
        }
        std::cout << i << " ";
    }
    std::cout << std::endl;
}
```

- `continue`
```cpp
#include <iostream>

int main() {
    for(int i = 0; i < 10; i++) {
        if(i % 2 != 0) {
            continue;
        }
        std::cout << i << " ";
    }
    std::cout << std::endl;
}
```

ასევე არსებობს `for` ციკლის მეორე სახეობა რომელსაც დიაპაზონიან `for`-ს ეძახიან.

- დიაპაზონიანი `for`-ის სინტაქსი:
```cpp
for(ელემენტი : კონტეინერი) {
    // კოდი 
}
```
დიაპაზონიანი `for` ციკლი ავტომატურად ახდენს იტერაცის რომელიმე კონტეინერის ტიპის
ცვლადზე. ეს ხაზი: `for(ელემენტი : კონტეინერი)` შეგვიძლია ასე წავიკითხოთ:
\"ყოველი ელემენტისათვის კონტეინერში\"


- გამოყენების მაგალითი
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> nums = { 54, 123, 5, 12, 65, 41 };

    for(int num : nums) {
        std::cout << num << " ";
    }
    std::cout << std::endl;
}
```


# 13.break შეტყობინება.რომელი შეტყობინებები იყენებს მას.შინაარსი მაგალითები.
`break` მთლიანად დაასრულებს ციკლს და პროგრამა გადავა შემდეგ ციკლის შემდეგ
მყოფ განაცხადზე.

```cpp
#include <iostream>

int main() {
    int count = 0;

    while(count < 10) {
        if(count == 6) {
            break;
        }

        std::cout << count << " ";
        count++;
    }
    std::cout << std::endl;
}
```
ეს პროგრამა დაბეჭდავს რიცხვებს 5-ის ჩათვლით რის შემდეგაც მივალთ `break`
განაცხადთან რომელიც ჩვენ ციკლს დაასრულებს, რის შემდეგაც პროგრამა გადავა
შემდეგ განაცხადზე რომელიც არის ახალი ხაზის დაბეჭდვა და დაასრულებს მუშაობას
მისი შესრულების მერე.


# 14.continue შეტყობინება. რომელი შეტყობინებები იყენებს მას.შინაარსი მაგალითები.
`continue` დაასრულებს ციკლის ეხლანდელ იტერაციას და გადავა შემდეგ იტერაციაზე.
```cpp
#include <iostream>

int main() {
    int count = 0;

    while(count < 10) {
        if(count % 2 != 0) {
            break;
        }

        std::cout << count << " ";
        count++;
    }
    std::cout << std::endl;
}
```


# 15.სტრინგი. მისი შინაარსი და საჭიროება მოკლე მაგალითებით. სტინგის კლასის რამდენიმე მეთოდი მაგალითებით. 
`std::string` არის ტექტის დამუშავების პრობლემის გადაჭრა, რომ დავფიქრდეთ, ტექსტი
უბრალოდ სიმბოლოების მასივია, ზუსტად ეს დევს `std::string` კლასის შიგნით, მაგრამ
იმის გარდა რომ ეს კლასი გვაძლევს ტექტის გამოსახვის და შენახვის შესაძლებლობას მას
ასევე მოყვება მრავალი დამატებითი, მოსახერხებელი ფუნქციონალი:

- მარტივი გამოყენების მაგალითი:
```cpp
#include<iostream>
#include<string>

int main() {
    std::string message = "Hello World!";

    std::cout << message << std::endl;
}
```

- კონკატენაცია
```cpp
#include <iostream>
#include <string>

int main() {
    std::string str1 = "Hello, ";
    std::string str2 = "wordl!";
    
    std::string message = str1 + str2;  
    std::cout << message << std::endl;  
}
```

- რამოდენიმე `std::string` კლასის მეთოდი
```cpp
std::string message = "Hello World!";
message.size();        // დააბრუნებს მესიჯის სიგრძეს

// პარამეტრად იღებს სასურველი ქვე-string-ის 
// პირველი და მეორე სიმბოლოების პოზიციებს
message.substr(5, 11); // დააბრუნებს მესიჯის ქვე-string-ს

// პარამეტრად იღებს სასურველ ქვე-string-ს
message.find("llo"); // დააბრუნებს ქვე-string-ის პირველი სიმბოლოს პოზიციას

// პარამეტრად იღებს სასურველ სიმბოლოს
message.push_back('!'); // მესიჯის ბოლოში დაამატებს სიმბოლოს და გაზრდის მის ზომას 1-ით

message.clear(); // წაშლის ყველაფერს მესიჯიდან და დატოვებს მასში ცარიელ string-ს
```


# 16. ვექტორი. მისი შინაარსი და საჭიროება მოკლე მაგალითებით. ვექტორის კლასის რამდენიმე მეთოდი მაგალითებით.
`std::vector<T>` არის ერთერთი კონტენერი სტანდარტული ბიბლიოთეკიდან, იგი არის
დინამიური მასივი რომლის ზომაც დამოკიდებულია მასში მყოფი ელემენტების რაოდენობაზე.
ხშირად არის შემთხვევა როცა შემომავალი მონაცემების რაოდენობა ჩვენთვის უცნობია,
ამიტომაც სტანდარტული მასივის ფიქსირებული ზომა დაბრკოლებად ხდება ჩვენთვის.
ამ პრობლემას აგვარებს ვექტორი და მისი დინამიური ზომა, იგი შეძლებს ნებისმიერი
რაოდენობის ელემენტების დატევას, იგი ასევე არ კარგავს ელემენტებთან წვდომის სწრაფ
მეთოდს რადგან სტანდატული მასივისნაირად, ელემენტებს მეხსიერებაში გვერდიგვერდ
ინახავს.

- სინტაქსი
```cpp
std::vector<ტიპი> სახელი;
```

- გამოყენების მაგალითი

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> nums;
    
    int data;
    while (std::cin >> data) {
        nums.push_back(data);
    }

    for (int num : nums) {
        std::cout << num << " ";
    }
    std::cout << std::endl;
}
```
ეს პროგრამა მომხმარებლისგან წაიკითხავს n რაოდენობის მონაცემს, შეინახავს ვექტორში
და დაბეჭდავს მათ.

- რამოდენიმე `std::vector<T>` კლასის მეთოდი
```cpp

```


