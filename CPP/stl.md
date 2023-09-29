---
title: STL 入门
author:情久小羊
date: 2021-01-14
---

## 标准模板库（STL）

STL 即标准模板库（Standard Template Library），是 C++ 标准库的一部分，里面包含了一些模板化的通用的数据结构和算法。由于其模板化的特点，它能够兼容自定义的数据类型，避免大量的造轮子工作。NOI 和 ICPC 赛事都支持 STL 库的使用，因此合理利用 STL 可以避免编写无用算法，并且充分利用编译器对模板库优化提高效率。

## 迭代器

在 STL 中，迭代器（Iterator）用来访问和检查 STL 容器中元素的对象，它的行为模式和指针类似，但是它封装了一些有效性检查，并且提供了统一的访问格式。

### 基础使用

概念虽然晦涩难懂，但是在使用时可以当作指针，迭代器常用的两个运算符：自增 （ `++` ） 和解引用（单目 `*` 运算符），其中自增用来移动迭代器，解引用可以获取或修改它指向的元素。

### 迭代器分类

#### 前向迭代器

支持通过 `++` 自增（前移），通过 `*` 访问或赋值。

```cpp {10-11}
#include <iostream>
#include <forward_list>
using namespace std;

int main() {
    // forward_list 是 STL 中的单向链表，可以获得前向迭代器
    forward_list<int> l{1, 2, 3};

    forward_list<int>::iterator iter = l.begin();
    for (; iter != l.end(); ++iter) {
        cout << *iter << ' ';  // 输出: 1 2 3
    }
    return 0;
}
```

#### 双向迭代器

在前向迭代器的基础上，增加了自减（`--`）的支持。

```cpp {16}
#include <iostream>
#include <list>
using namespace std;

int main() {
    // list 是 STL 中的双向链表，可以获得双向迭代器
    list<int> l{1, 2, 3};

    list<int>::iterator iter = l.begin();
    for (; iter != l.end(); ++iter) {
        cout << *iter << ' ';  // 输出: 1 2 3
    }
    cout << endl;

    while (iter != l.begin()) {
        --iter;
        cout << *iter << ' ';  // 输出: 3 2 1
    }
    return 0;
}
```

#### 随机访问迭代器

在双向迭代器的基础上，增加了加减运算和比较运算的支持。

```cpp {9}
#include <iostream>
#include <vector>
using namespace std;

int main() {
    // vector 是 STL 对数组的封装
    vector<int> v{1, 2, 3, 4, 5};

    for (vector<int>::iterator iter = v.begin(); iter < v.end(); iter += 2) {
        cout << *iter << ' ';  // 输出: 1 3 5
    }
    return 0;
}
```

## vector

vector 是 STL 提供的 **内存连续的** 、 **可变长度** 的数组（亦称列表或向量）数据结构。能够提供线性复杂度的插入和删除，以及常数复杂度的随机访问。

### 特性

#### 动态分配内存 <Badge type="tip" text="重点" />

很多时候我们不能提前开好那么大的空间。尽管我们能知道数据总量在空间允许的级别，但是单份数据还可能非常大，这种时候我们就需要 vector 来把内存占用量控制在合适的范围内。 vector 还支持动态扩容，在内存非常紧张的时候这个特性就能派上用场了。

### 构造函数

```cpp
// 创建空 vector
vector<int> v1;

// 创建一个初始长度为 3 的 vector，元素默认值为 0
vector<int> v2(3);

// 创建一个初始长度为 3 的 vector，元素默认值为 2
vector<int> v3(3, 2);

// C++11 初始化列表
vector<int> v4{1, 2, 3, 4};

// 拷贝构造
vector<int> v5(v4);

// 拷贝 v4 的部分内容，也就是 {2, 3}
vector<int> v6(v4.begin() + 1, v4.begin() + 3);
```

### 成员函数

#### 元素访问

- `at()` 访问指定的元素，同时进行越界检查，越界则抛出异常。
- `operator[]` 重载了 `[]` ，可以像普通数组一样通过 `v[index]` 访问。
- `front()` 返回第一个元素的值。
- `back()` 返回最后一个元素的值。
- `data()` 返回指向内存中数组第一个元素的指针。

#### 迭代器

- `begin()` 返回指向起始的迭代器。
- `end()` 返回指向末尾的迭代器。
- `rbegin()` 返回指向起始的逆向迭代器。
- `rend()` 返回指向末尾的逆向迭代器。

#### 容量

- `empty()` 检查容器是否为空。
- `size()` 返回容纳的元素数。
- `max_size()` 返回容器大小的理论极限，这个值通常会受内存限制。
- `reserve()` 预先申请存储空间。（修改 `capacity`）
- `capacity()` 返回当前存储空间能够容纳的元素数。
- `shrink_to_fit()` 释放未使用的内存减少内存的使用（减小 `capacity` 到 `size`）

#### 修改

- `clear()` 清空内容。
- `insert()` 插入元素。
- `emplace()` 原位构造元素。（可以理解为更高效的插入）
- `erase()` 删除元素。
- `push_back()` 将元素添加到容器末尾。
- `emplace_back()` 在容器末尾就地构造元素。
- `pop_back()` 移除末元素。
- `resize()` 改变容器中可存储元素的个数。（修改 `size`）
- `swap()` 交换内容。

### 示例代码

::: tip
最好复制去自己运行一遍，思考一下结果。
:::

动态分配内存

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v;
    for (int i = 0; i < 20; ++i) {
        v.push_back(i);
        cout << "size = " << v.size()
             << ",\tcapacity = " << v.capacity()
             << endl;
    }
    return 0;
}
```

杨辉三角

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v;
    int n;
    cin >> n;
    for (int i = 0; i < n; ++i) {
        v.push_back(1);
        for (int j = i - 1; j > 0; --j) {
            v[j] += v[j - 1];
        }
        for (int num : v) {
            cout << num << ' ';
        }
        cout << endl;
    }
    return 0;
}
```

## 参考资料

- [cppreference](https://zh.cppreference.com/w/%E9%A6%96%E9%A1%B5)
- [STL 教程：C++ STL 快速入门](http://c.biancheng.net/stl/)

