# STL序列式容器 - 导言

## 内容目录

- [什么是容器和迭代器](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/0STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8%20-%20%E5%AF%BC%E8%A8%80.md)
- [数组容器 array](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/1%E6%95%B0%E7%BB%84%E5%AE%B9%E5%99%A8array.md)
- [向量容器 vector](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/2%E5%90%91%E9%87%8F%E5%AE%B9%E5%99%A8vector.md)
- [双端队列容器 deque](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/3%E5%8F%8C%E7%AB%AF%E9%98%9F%E5%88%97%E5%AE%B9%E5%99%A8deque.md)
- [链表容器 list](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/4%E9%93%BE%E8%A1%A8%E5%AE%B9%E5%99%A8list.md)
- [正向链表容器 forward_list](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/5%E6%AD%A3%E5%90%91%E9%93%BE%E8%A1%A8%E5%AE%B9%E5%99%A8forward_list.md)



## 什么是容器？

简单的理解容器，它就是一些模板类的集合，但和普通模板类不同的是，容器中封装的是组织数据的方法（也就是数据结构）

STL 提供有三类标准容器，分别是 **序列容器**、**排序容器** 和 **哈希容器**。

| 种类     | 功能                                                         |
| -------- | ------------------------------------------------------------ |
| 序列容器 | 元素在容器中的位置同元素的值无关，即容器不是有序的。（vector / list / deque) |
| 排序容器 | 元素默认是由小到大排序的，即便是插入元素，元素也会插入到适当位置。（set / multiset / map / multimap） |
| 哈希容器 | 元素是未排序的，元素的位置是由哈希函数确定的。（unordered_set / unordered_multiset / unordered_map / unordered_multimap） |





## 什么是迭代器？

### 定义

无论选用哪种容器，最常作的操作无疑是**遍历容器中存储的元素**，该操作多数情况会选用 “**迭代器（iterator）**” 来实现。

简单来讲，迭代器和C++的指针非常类似，它可以是需要的任意类型，通过迭代器可以指向容器中的某个元素，如果需要，还可以对该元素进行读/写操作。



### 类别

STL标准库为每一种标准容器定义了一种迭代器类型。

> 不同容器的迭代器不用，其功能强弱也有所不同。

常用的迭代器按功能强弱分为五种：输入迭代器、输出迭代器、前向迭代器、双向迭代器、随机访问迭代器。



#### 1. 输入迭代器



#### 2. 输出迭代器





#### 3. 前向迭代器（forward iterator）

假设 p 是一个前向迭代器，则 p 支持：

- 可以进行 `++p` / `p++` / `*p` 操作
- 可以被复制或赋值
- 可以用 == 和 != 运算符进行比较
- 两个正向迭代器可以互相赋值



#### 4. 双向迭代器（bidirectional iterator）

假设 p 是一个双向迭代器，则 p 支持

- 正向迭代器的全部功能
- 可以进行 `--p` / `p--` 操作



#### 5. 随机访问迭代器（random access iterator）

假设 p 是一个随机访问迭代器，则 p 支持

- 双向迭代器的全部功能
- 可以进行 `p+=i` / `p-=i` / `p+i` / `p-i` / `p[i]`
- 两个随机访问迭代器 p1/p2 可以用 > < <= >=运算符进行比较



### 不同容器指定使用的迭代器类型

- **随机访问迭代器**：array / vector / deque / list
- **双向迭代器**：list / set / multiset / map / multimap
- **前向迭代器**：forward_list / unordered_map / unordered_multimap / unordered_set / unordered_multiset
- **不支持迭代器**：stack / queue



### 定义方式

- 正向迭代器

```c++
// 容器类名::iterator 迭代器名;
```

- 常量正向迭代器

```c++
// 容器类名::const_iterator 迭代器名;
```

- 反向迭代器

```c++
// 容器类名::reverse_iterator 迭代器名;
```

- 常量反向迭代器

```c++
// 容器类名::const_reverse_iterator 迭代器名;
```

> `*迭代器名` 就表示读取该迭代器指向的元素。



### 示例

```c++
#include <iostream>
#include <vector>

using namespace std;

int main() {
    // 普通遍历
    vector<int> v{1,2,3,4,5,6,7};
    for (int i = 0; i < v.size(); i++) {
        cout << v[i] << " ";
    }
    cout << endl;
    
    // 迭代器遍历
    vector<int>::iterator i;
    for(i = v.begin(); i != v.end(); i++) {
        cout << *i << " ";
    }
}
```



> 在C++中，数组也是容器。数组的迭代器就是指针，而且是随机访问迭代器。



## 序列式容器

所谓序列式容器，即以线性排列来存储某一特定类型的数据。该类容器不会自动对存储的元素按值的大小进行排序。

序列容器分为以下几类：



- [数组容器](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/1%E6%95%B0%E7%BB%84%E5%AE%B9%E5%99%A8array.md) `array<T,N>`
  - 可以存储 N 个 T 类型的元素，是C++本身提供的一种容器。
  - 容器一旦建立，长度固定不变。
- [向量容器](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/2%E5%90%91%E9%87%8F%E5%AE%B9%E5%99%A8vector.md) `vector<T>`
  - 存储 T 类型的元素，长度可变，即在存储空间不足时，会自动申请更多的内存。
  - 在尾部增加或删除元素的效率最高。在其他位置插入或删除元素效率较差。
- [双端队列容器](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/3%E5%8F%8C%E7%AB%AF%E9%98%9F%E5%88%97%E5%AE%B9%E5%99%A8deque.md) `deque<T>`
  - 存储 T 类型的元素，长度可变。
  - 在尾部插入和删除元素高效，在头部插入和删除元素同样高效。但在中间某一位置插入或删除元素效率较差。
- [链表容器](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/4%E9%93%BE%E8%A1%A8%E5%AE%B9%E5%99%A8list.md) `list<T>`
  - 存储 T 类型的元素，长度可变。
  - 以**双向链表**的形式组织元素，在这个序列的任何地方都可以高效地增加或删除元素。
  - 但访问容器中任意元素的速度要比前三种容器慢，因为必须从第一个元素或最后一个元素起，沿着链表查找。
- [正向链表容器](https://github.com/SLEEPYDOG77/C-Notes/blob/develop/C%2B%2BSTL%E5%BA%93/%E7%AC%AC2%E7%AB%A0%20STL%E5%BA%8F%E5%88%97%E5%BC%8F%E5%AE%B9%E5%99%A8/5%E6%AD%A3%E5%90%91%E9%93%BE%E8%A1%A8%E5%AE%B9%E5%99%A8forward_list.md) `forward_list<T>`
  - 存储 T 类型的元素，长度可变。
  - 以**单链表**的形式组织元素，它内部的元素只能从第一个元素开始访问。
  - 是一类比链表容器快、更节省内存的容器。

> `stack<T>` 和 `queue<T>` 本质上也属于序列容器，它们都是在 deque 的基础上改造而成，通常称它们为**容器适配器**。