# 最小生成树

## Kruskal

步骤：<br>
* 按照权值大小将边排序并保存到数组V中
* 遍历V,连接节点
* 判断是否有环路，如果有舍去，反之保留
* 直到全部节点被连接

## Prim

步骤：<br>
* 指定一个节点，设为selected
* 将selected和no selected的分别作为两个整体
* 从selected到no selected选择权值最小的边，并将节点计入到selected
* 过程中不可以出现环
* 直到节点全部被连接

# 树的存储结构

* 双亲表示法
```C++
//parent = -1表示无双亲
template<class DataType>
struct PNode{
    DataType Data;
    int parent;
}
```
* 带右兄弟的双亲表示法
```C++
//parent = -1表示无双亲,rightsib = -1表示无右兄弟
template<class DataType>
struct PNode{
    DataType Data;
    int parent;
    int rightsib;
}
```
* 孩子表示法
```C++
struct CTNode{
    int Child;
    CTNode *Next;
}
template <Class DataType>
struct CBNode{
    DataType Data;
    CTNode *FirstChild;
}

vector<CBNode<int>>v;
//只表示孩子
```
* 双亲孩子表示法
* 孩子兄弟表示法

| firstchild | data | rightsib |
| ---- | ---- | ----- |


# 二叉树性质

* $n_0 = n_2+1$

# 完全二叉树

* $k=\lfloor log_2n \rfloor +1$
* 编号为 $i$ 的双亲编号 $\lfloor i/2 \rfloor$
* 编号为 $i$ 的左孩子编号 $2i$

# 二叉树的存储方式

* 顺序存储，使用数组保存二叉树的满二叉树形式
* 链式存储，`lchild data rchild`
* 三叉链表，`lchild data rchild parent`
* 线索链表，`ltag lchild data rchild rtag` tag=0指向孩子否则指向前驱或后继

```Cpp
//枚举
enum class flag{
    Child,Thread
};
//定义节点
template <class DataType>
struct ThrNode{
    DataType data;
    ThrNode<DataType> *lchild,*rchild;
    flag ltag,rtag;
};
//先建立二叉链表
template <class DataType>
ThrNode<DataType>* Creat(ThrNode<DataType>*bt){
    cin>>ch;
    if(ch=='#')bt=NULL;
    else{
        bt = new ThrNode;bt->data = ch;
        bt->ltag = 0;bt->rtag = 0;
        bt->lchild = Creat(bt->lchild);
        bt->rchild = Creat(bt->rchild);
    }
    return bt;
}
//中序线索化链表
template <class DataType>
ThrNode<DataType>* InitThrBiTree(ThrNode<DataType>*bt){
//
}
```