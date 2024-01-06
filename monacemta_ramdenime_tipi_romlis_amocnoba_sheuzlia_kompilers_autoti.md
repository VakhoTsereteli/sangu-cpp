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