**1. Static allocation**
	Cấp phát bộ nhớ cho một đối tượng ở Compilation time, thường dùng cho biến global hoặc static local.
**2. Stack Dynamic Allocation**
	Cấp phát tự động vào stack ở Runtime, thường dùng cho biến ở trong hàm. Cấp phát bộ nhớ xảy ra khi một hàm được gọi và hủy cấp phát xảy ra khi hàm trả về. Việc cấp phát và hủy cấp phát được quản lý tự động bởi trình biên dịch.
**3. Explicit Heap Dynamic Allocation**
	Bộ nhớ được cấp phát vào heap ở runtime. Phải phân bổ và giải phóng bộ nhớ một cách thủ công bằng cách sử dụng các hàm như `malloc()` và `free()` trong C, hoặc `new` và `delete` trong C++.
**4. Implicit Heap Dynamic Allocation**
	Cấp phát bộ nhớ trên heap ở runtime, nhưng việc hủy cấp phát bộ nhớ được quản lý tự động. Không cần phải giải phóng bộ nhớ một cách thủ công.

**Ví dụ minh họa**
```
#include <iostream>

using namespace std;

// Static Allocation (global variable)
int staticVariable = 10;

int main() {
    // Stack Dynamic Allocation
    int stackVariable = 5;
    
    // Explicit Heap Dynamic Allocation
    int* explicitHeapVariable = new int(20);
    
    // Implicit Heap Dynamic Allocation
    int* implicitHeapVariable = new int(30);
	
	// This is just an example
	// In fact, there is no built-in support for implicit heap dynamic allocation in 
	// C++. However, languages like Java or C# employ automatic garbage collection, 
	// which implicitly manages the memory deallocation for objects that are no longer
	// referenced.
	
    // Accessing and printing the values
    cout << "Static variable: " << staticVariable << endl;
    cout << "Stack variable: " << stackVariable << endl;
    cout << "Explicit heap variable: " << *explicitHeapVariable << endl;
    
    cout << "Implicit heap variable: " << *implicitHeapVariable << endl;
    // Deallocating explicitly allocated heap memory
    delete explicitHeapVariable;
    
    // The implicit heap variable does not require explicit deallocation
    
    return 0;
}
```