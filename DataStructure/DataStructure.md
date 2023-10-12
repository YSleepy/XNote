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

# 普通树的性质

* 树的结点数等于所有结点度数和加一
* 树的路径长度是从根到每个结点的路径长度之和

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

# （二叉树）的前序遍历和后序遍历

* 当前序遍历XY后续遍历YX一定有X是Y的父亲结点


# 哈夫曼树前缀码

* 定义：在一个字符集中，任何一个字符编码都不是另一个字符编码的前缀。

# AOE网络关键路径

* `事件最早发生时间ve`：按拓扑排序顺序遍历求值，当前结点为i,i.pre为i的前缀节点，VE(源点)=0，VE(i)=max(i.pre+path)
* `事件最晚发生时间vl`：按逆拓扑排序顺序遍历求值，当前结点为i,i.next为i的后缀节点，VL(源点)=VE(源点),VL(汇点)=VE(汇点)，VE(i)=min(i.next-path)
* `活动最早开始时间e`：e=边始点的最早发生时间ve
* `活动最晚开始时间l`：边终点的vl-path
* `全部关键路径`：保留在e=l的边，以箭头的方向为顺序排列边即可得到，在有多个关键路径时只有同时减少多个关键路径共有边才可缩短工期。
* `活动的时间余量`：边终点的VL-边始点的VE-path

# Dijkstra 最短路径
步骤<br>
* 起点为0并更新后继所有结点，起点加入集合S
* 选择已更新结点中最小加入集合S并更新最小节点后继

# 邻接表

* AOV的拓扑排序：时间复杂度O(n+e)

步骤：<br>
1. 先遍历一次节点数组，将入度为0的添加的栈顶
2. 栈非空，输出栈顶元素。并记录输出结点个数count，循环2-3
3. 遍历该节点对应的边，使终点结点入度减一，如果结点入度为零则添加到栈
4. 如果count<结点数则有回路
   
# 邻接矩阵