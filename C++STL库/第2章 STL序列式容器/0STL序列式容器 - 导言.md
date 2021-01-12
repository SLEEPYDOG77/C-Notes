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

无论选用哪种容器，最常作的操作无疑是遍历容器中存储的元素，该操作多数情况会选用 “迭代器（iterator）” 来实现。

简单来讲，迭代器和C++的指针非常类似，它可以是需要的任意类型，通过迭代器可以指向容器中的某个元素，如果需要，还可以对该元素进行读/写操作。



### 类别

STL标准库为每一种标准容器定义了一种迭代器类型。

> 不同容器的迭代器不用，其功能强弱也有所不同。



