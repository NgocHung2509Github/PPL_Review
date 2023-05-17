### Description
___
Là quá trình liên kết giữa *tên* (name) và *giá trị* (value) trong một chương trình máy tính. Trong lập trình, khi bạn tạo một *biến* (variable), bạn đang tạo một *tên* để đại diện cho một giá trị. **Binding** là quá trình gán giá trị cho biến và xác định cách thức truy cập đến biến đó trong chương trình.

### Types of binding
___
**1. Early binding (Static binding):** là quá trình liên kết được thực hiện tại thời điểm biên dịch (compilation time). *Giá trị* được liên kết với *tên biến* khi chương trình được biên dịch. Điều này có thể giúp tăng tốc độ chương trình khi nó được thực thi, vì biên dịch đã sẵn sàng các liên kết trước đó.
**2. Late binding:** là quá trình liên kết được thực hiện tại thời điểm chương trình được thực thi (runtime). Thay vì gán *giá trị* cho *biến* khi chương trình được biên dịch, giá trị được gán vào biến khi chương trình đang chạy. Điều này cho phép chương trình được linh hoạt hơn trong việc thay đổi *giá trị* của *biến* và chức năng của nó.
**3. Dynamic binding:** là quá trình liên kết được thực hiện dựa trên *kiểu* (type) của *đối tượng* (object) đang được sử dụng. Khi một *đối tượng* được tạo, giá trị của nó được liên kết với kiểu đối tượng đó. Khi đối tượng được sử dụng trong chương trình, phương thức được gọi được liên kết động với đối tượng dựa trên kiểu của nó.

### Alias
___
Alias là một khái niệm để chỉ định rằng hai hoặc nhiều biến có cùng một vùng nhớ hoặc địa chỉ. Khi bạn tạo một alias, bạn có nhiều biến cùng trỏ đến cùng một vùng nhớ, và việc thay đổi giá trị của một biến sẽ ảnh hưởng đến tất cả các biến khác trỏ đến cùng vùng nhớ đó. Alias có thể tạo ra bằng cách gán một biến cho một biến khác hoặc thông qua tham chiếu đến đối tượng.
Ví dụ 1:
```
x = 10
y = x  # tạo alias, y trỏ đến cùng vùng nhớ với x
print(x)  # 10
print(y)  # 10

y = 20  # thay đổi giá trị của y
print(x)  # 10 (giá trị của x không thay đổi)
print(y)  # 20
```
Ví dụ 2:
```
#include <iostream>

using namespace std;

int main() {
    int x = 10;
    int* ptr = &x;  // Tạo con trỏ ptr trỏ đến x
    int& ref = x;   // Tạo tham chiếu ref đến x

	cout << "Initial values:" << endl;
    cout << "x: " << x << endl;
    cout << "ptr: " << *ptr << endl;
    cout << "ref: " << ref << endl;

    *ptr = 20;  // Thay đổi giá trị của biến được trỏ bởi ptr
    cout << "\nAfter modifying value through pointer:" << std::endl;
    cout << "x: " << x << endl;
    cout << "ptr: " << *ptr << endl;
    cout << "ref: " << ref << endl;

    ref = 30;  // Thay đổi giá trị của biến được tham chiếu bởi ref
    cout << "\nAfter modifying value through reference:" << std::endl;
    cout << "x: " << x << endl;
    cout << "ptr: " << *ptr << endl;
    cout << "ref: " << ref << endl;

    return 0;
}
```
Trong ví dụ này, chúng ta khởi tạo một biến `x` với giá trị ban đầu là 10. Sau đó, chúng ta tạo một con trỏ `ptr` trỏ đến biến `x` bằng cách gán địa chỉ của `x` cho `ptr`. Chúng ta cũng tạo một tham chiếu `ref` đến `x` bằng cách khai báo `ref` là một tham chiếu đến `x`.

Sau đó, chúng ta thực hiện các thay đổi giá trị thông qua con trỏ `ptr` và tham chiếu `ref`. Khi chúng ta thay đổi giá trị của biến được trỏ bởi `ptr` hoặc biến được tham chiếu bởi `ref`, giá trị của `x` cũng thay đổi theo. Điều này cho thấy rằng con trỏ và tham chiếu đang tạo alias cho biến `x`.

Kết quả đầu ra của chương trình sẽ là:
```
Initial values:
x: 10
ptr: 10
ref: 10

After modifying value through pointer:
x: 20
ptr: 20
ref: 20

After modifying value through reference:
x: 30
ptr: 30
ref: 30
```

### Polymorphism
___
Polymorphism là khả năng của đối tượng hoặc hàm để có thể đại diện cho nhiều kiểu dữ liệu khác nhau. Trong polymorphism, một phương thức có thể có nhiều hình thái hoặc hành vi khác nhau dựa trên kiểu đối tượng được gọi. Polymorphism thường được thực hiện thông qua kỹ thuật ghi đè phương thức (method overriding) hoặc giao diện (interface) trong các ngôn ngữ hướng đối tượng.

Ví dụ:
```
#include <iostream>

using namespace std;

class Animal {
public:
    virtual void makeSound() {
        cout << "Animal makes a sound" << endl;
    }
};

class Dog : public Animal {
public:
    void makeSound() override {
        cout << "Dog barks" << std::endl;
    }
};

class Cat : public Animal {
public:
    void makeSound() override {
        cout << "Cat meows" << endl;
    }
};

int main() {
    Animal* animalPtr;
    
    Dog dog;
    Cat cat;
    
    animalPtr = &dog;
    animalPtr->makeSound();  // "Dog barks"
    
    animalPtr = &cat;
    animalPtr->makeSound();  // "Cat meows"

    return 0;
}
```

Trong ví dụ này, chúng ta có một lớp cơ sở `Animal` với một phương thức `makeSound()` được khai báo là ảo (virtual). Lớp `Dog` và `Cat` kế thừa từ `Animal` và ghi đè phương thức `makeSound()` để cung cấp hành vi riêng của chúng.

Trong hàm `main()`, chúng ta tạo một con trỏ `animalPtr` kiểu `Animal`. Sau đó, chúng ta tạo một đối tượng `Dog` và một đối tượng `Cat`. Bằng cách gán địa chỉ của đối tượng `Dog` và `Cat` cho con trỏ `animalPtr`, chúng ta có thể gọi phương thức `makeSound()` thông qua con trỏ và xác định phương thức cụ thể được gọi dựa trên kiểu đối tượng thực tế.

Kết quả đầu ra của chương trình sẽ là:
```
Dog barks
Cat meows
```

Điều này chứng tỏ sự linh hoạt của polymorphism, trong đó cùng một phương thức `makeSound()` có thể có nhiều hình thái khác nhau dựa trên kiểu đối tượng thực tế được tham chiếu.