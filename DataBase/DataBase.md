# 数据库概念
## 数据库系统

* 数据库系统构成：数据库，数据库管理系统，应用程序，数据库管理员
* 数据库系统组成：硬件，数据库，软件，人员
* 数据独立性：物理独立性，逻辑独立性，指的是应用程序与数据库之间的独立性。通过二级映像来保证

## 数据模型

* 描述了静态特征，动态行为，约束条件；分别对应数据结构（层次结构，网状结构，关系结构），数据操作，数据的约束条件
* 分类：1概念模型，2逻辑模型和物理模型
* 概念模型：面向用户，面向客观世界。E-R图

* 实体完整性：每一个数据都应该有他唯一的关键字（主键，属性或属性集合）
* 参照完整性：联系中的属性必须参照外键对应的值，比如：学生和成绩，成绩里的学号一定是学生里有的
* 用户定义的完整性：比如0<=成绩<=100;

* 在计算机学科中透明就是不可见的意思

* 实体：人
* 属性：眼睛，腿
* 实体型：人（眼睛，腿）；实体和属性集合一同刻画
* 实体集：全体的人
* 联系：实体内部，实体间都可以有联系；班长和学生，学生和老师
* 关系模式：R（U,D,DOM,F）U=关系属性名集合，D=属性的取值范围，DOM（属性名-域），F=属性间数据依赖关系集合
* 关系模式是模板，关系是通过关系模式这个模板得到的实际内容，关系模式就像表的定义，关系就像有数据的表
* 关系数据库型：对关系数据库的描述
* 关系数据库模式：定义若干域，在定义若干关系模式
* 关系数据库值：在某一时刻保存的关系的集合

# 计算机系统的安全模型

* 用户鉴定
* 数据库安全控制保护：审计等
* 操作系统安全
* 数据密码存储

# 数据库安全控制

* 用户身份鉴别：静态，动态，生物，智能卡鉴别
* 存取控制：定义用户权限，合法权限检查
* 审计
* 视图
* 数据加密

## 三级模式结构

* 外模式：视图，查询到的结果视图
* 外模式/模式映像：
* 模式：基本表
* 内模式/模式映像：映像就是转换
* 内模式：数据索引

# 关系数据库

# 术语


* <span style="color: pink;">域</span>：属性的取值范围
* <span style="color: pink;">笛卡尔积 $\times$</span>：给定n个域，n个域可以相同也可以不同。参考域的解释，笛卡尔积就是各个域内部元素排列组合。笛卡尔积的结果有部分数据可能无意义。
* <span style="color: pink;">元组</span>：笛卡尔积中的每一个元素称作一个元组
* <span style="color: pink;">分量</span>：元组中属性的值称为分量
* <span style="color: pink;">基数</span>：域中元素个数，笛卡尔积的基数，各个域基数的乘积。
* 笛卡尔积可以表示为一个二维表，表的一行就是一个元组，每一列对应一个域。
* <span style="color: pink;">关系</span>：R(属性，属性···)
* <span style="color: pink;">候选码</span>：可唯一标识元组的属性组
* <span style="color: pink;">主属性</span>：候选码的属性称为主属性
* <span style="color: pink;">非主属性</span>：除了主属性
* <span style="color: pink;">基本表</span>：实际存储的表，实际存储数据的逻辑表示
* <span style="color: pink;">查询表</span>：查询结果对应的表
* <span style="color: pink;">视图表</span>：由基本表或其他视图表导出的表，是虚表，不对应实际存储数据


# 表特性

* 不同的列可以出至同一个域
* 行和列都是无序的
  
# 关系模型的定义规范

* 实体完整性：必须有主键，不为空，不重复，主属性全不能为空
* 参照完整性：可以在同一个表内

EmployeeID：员工的唯一标识（主键）。<br>
ManagerID：员工的直接上级经理的员工ID，它是对自身表中的EmployeeID的外键引用。<br>

|EmployeeID | ManagerID | Name|
|---------|-----------|--------
1         | NULL      | Alice
2         | 1         | Bob
3         | 1         | Carol
4         | 2         | David
5         | 2         | Eve

# 关系代数

传统集合运算
* 并$\cup$
* 差$-$：$R-S,在R但不在S$
* 交$\cap$
* 笛卡尔积$\times$：
 
专门的关系运算
* 选择$\sigma$：$\sigma _{条件}(表名)$，结果有原来的全部属性
* 投影$\pi$：$\pi _{属性名}(表名)$，去掉重复行
* 连接⋈：$表名\underset{属性(条件)属性}{⋈}表名，$ 自然连接要去掉重复的列。连接时会丢弃一些无法关联的行（悬浮元组）
* 外连接：保留悬浮元组，其他属性填NULL
* 左外连接：只保留左边关系的悬浮元组
* 右外连接：你懂的
* 除$\div$：R(A,B),S(B,C,D···)。设集合W满足一下条件：R中属性A所有元素的象集包含$\pi _B(S)$。那么W就是R$\div$S。
* 除数据库意义：eg：选择了所有课程的学生号。eg：至少选择了语文和英语课程的学生。

补充说明：<br>
象集：求$x_1,x_2,x_3$在关系R上的象集<br>
||R||
|---|---|---|
|x1|z1|
|x1|z2|
|x1|z3|
|x2|z1|
|x3|z3|
$Z_{x1}=\{z1,z2,z3\}$同理求得其他

# MYSQL
只修改列的数据类型的方法:<br>
> alter table student modify column sname varchar(20);

同时修改列名和列的数据类型的方法:<br>
> alter table student change column sname stuname varchar(20);

# SQL

创建模式
> create schema <schema_name> aothorization <user_name>

删除模式,表
> drop schema <schema_name> [cascade|restrict]
> drop table <table_name>[cascade|restrict]


定义外键
> foregin (key) <key_name...> reference table_name(property)

定义主键
> primary key (key1,key2)

添加一列
> alter table <table_name> add column <column_name> <datetype> [constraint_name]

添加表级约束[primary key,foreign key,unique,check]
>alter table <table_name> add <constraint>

删除一列
> alter table <table_name> drop column <column_name>[cascade|restrict]

删除表级约束
> alter table <table_name> drop constraint <constraint_name>[cascade|restrict]

修改列类型
> alter table <table_name> alter column <column_name><type>

自身连接查找
> select first.col,second.col2 from table first,table second where first.no=second.no

外连接
> select table_col from table left outer join table on(table_col=table_col)

