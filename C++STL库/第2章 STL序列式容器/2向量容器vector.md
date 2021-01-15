# 向量容器 vector

## 概述

vector 容器常被称为向量容器，与 array 容器十分相似，都是对 C++ 普通数组的 “升级版”。

不同之处在于，array 实现的是静态数组，vector 实现的是动态数组。



vector 容器以类模板 `vector<T>` 的形式定义在 `<vector>` 头文件中，位于 `std` 命名空间内。

```c++
#include <vector>
using namespace std;
```



## 创建

```c++
// 创建一个int类型的vector
vector<int> values1;

// 创建时同时初始化
vector<int> values2{2,3,5,7,11,13,17,19};

// 创建含有20个元素的int类型的vector，默认初始值为0
vector<int> values3(20);

// 创建含有20个元素的int类型的vector，初始值均为2
vector<int> values4(20, 2);

// 用其他vector容器来创建新的vector
vector<char> value1(5, 'c');
vector<char> value2(value1);
```



## 成员函数

| 函数            | 说明                                     | 函数        | 说明                           |
| --------------- | ---------------------------------------- | ----------- | ------------------------------ |
| begin()         |                                          | cbegin()    |                                |
| end()           |                                          | cend()      |                                |
| rbegin()        |                                          | crbegin()   |                                |
| rend()          |                                          | crend()     |                                |
| size()          | 返回实际元素个数                         | max_size()  | 返回元素个数的最大值           |
| resize()        | 改变实际元素的个数                       | capacity()  | 返回当前容量                   |
| empty()         | 判断容器中是否有元素                     | reserve()   | 增加容器的容量                 |
| shrink_to_fit() | 将内存减少到等于当前元素实际所使用的大小 | operator[]  | 重载了[]运算符                 |
| at()            | 使用经过边界检查的索引访问元素           | front()     | 返回第一个元素的引用           |
| back()          | 返回最后一个元素的引用                   | data()      | 返回指向容器中第一个元素的指针 |
| assign()        | 将新元素替换原有内容                     | push_back() | 在序列的尾部添加一个元素       |
| pop_back()      | 移出序列尾部的元素                       | insert()    | 在指定的位置插入一个或多个元素 |
| erase()         | 移出一个元素或一段元素                   | clear()     | 移出所有的元素，容器大小变为0  |
| swap()          | 交换两个容器的所有元素                   | emplace()   | 在指定的位置直接生成一个元素   |
| emplace_back()  | 在序列尾部生成一个元素                   |             |                                |





## 示例

```c++

```

