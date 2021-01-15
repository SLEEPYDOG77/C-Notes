# 数组容器 array

## 概述

array 容器是 C++ 11 标准中新增的序列容器。

它就是在 C++ 普通数组的基础上，添加了一些成员函数和全局函数。在使用上，比普通数组更安全，且效率并没有因此变差。

array 容器的大小是固定的，无法动态的扩展或收缩。



## 定义

array 容器以类模板的形式定义在头文件 `<array>` ，并位于命名空间 `std` 中。

```c++
namespace std {
    template <typename T, size_t N>
    class array;
}
```



## 使用

```c++
#include <array>
using namespace std;

// 定义了一个容量为10的int型 array 容器
array<int, 10> values1;

// 也可以在定义的同时对其中元素的值进行初始化
array<int, 5> values2 = {1,2,3,4,5};
```



## 成员函数

| 成员函数            | 功能                                                 | 成员函数   | 功能                             |
| ------------------- | ---------------------------------------------------- | ---------- | -------------------------------- |
| begin()             | 返回指向容器第一个元素的随机访问迭代器               | cbegin()   | const属性迭代器                  |
| end()               | 返回指向容器最后一个元素之后一个位置的随机访问迭代器 | cend()     | const属性迭代器                  |
| rbegin()            | 返回指向最后一个元素的随机访问迭代器                 | crbegin()  | const属性迭代器                  |
| rend()              | 返回指向第一个元素之前一个位置的随机访问迭代器       | crend()    | const属性迭代器                  |
| size()              | 返回容器中当前元素的数量                             | max_size() | 返回容器中可容纳元素的最大数量   |
| empty()             | 判断容器是否为空                                     | at(n)      | 返回容器中 n 位置处元素的引用    |
| front()             | 返回容器中第一个元素的直接引用                       | back()     | 返回容器中最后一个元素的直接引用 |
| data()              | 返回一个指向容器首个元素的指针                       | fill(val)  | 将val赋值给容器中每个元素        |
| array1.swap(array2) | 交换array1和array2容器中的所有元素                   |            |                                  |



## 示例

```c++
#include <iostream>
#include <array>

using namespace std;

int main() {
    array<int, 4> values{};
    
    for(int i = 0; i < values.size(); i++) {
        values.at(i) = i;
    }
    
    cout << get<3>(values) <<endl;
    
    if (!values.empty()) {
        for(auto iter = values.begin(); iter < values.end(); iter++) {
            cout << *iter << " ";
        }
    }
}
```



## 访问元素的方法

### 访问单个元素

#### 1. 容器名[]

```c++
values[4];
```



#### 2. `at()` 成员函数

> at() 方法更安全，能有效避免越界访问。
>
> 当传给 at() 的索引是一个越界值时，程序会抛出 `std::out_of_range` 异常。

```c++
values.at(4);
```



#### 3. `get<n>` 模板函数

> 获取容器第 n 个元素。
>
> 该模板函数中，实参必须是一个在编译时可以确定的常量表达式。

```c++
array<int, 4> values{1,2,3,4};
cout << get<3>(values) << endl;
```



#### 4. `data()` 成员函数

> 返回指向容器首个元素的指针。

```c++
array<int, 4> values{1,2,3,4};
cout << *(values.data()+3) << endl;
```



### 访问多个元素

#### 1. 借助`size()`

```c++
array<int, 4> values{1,2,3,4};
    
for(int i = 0; i < values.size(); i++) {
    cout << values[i] << endl;
}
```



#### 2. 借助迭代器

```c++
array<int, 4> values{1,2,3,4};

for(auto iter = values.begin(); iter < values.end(); iter++) {
    cout << *iter << " ";
}
```

