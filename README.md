# kaoyan
19年零基础跨考中国科学技术大学计算机科学与技术专业经验分享
复试真题回忆
============

1.1笔试
-------

### 1.1.1 离散数学

1.$A∩C=B∩C$，$A∪B=B∪C$，能否得到$A=B$?

2.集合$A$上有$a，b$，若$f(a)=f(b)$，则$a R b$，求证$R$是$A$上的等价关系。

3.三个命题为真，求推理出一个结论(核心是$A→B，A→C$，则$A→B∧C$)

4.西电版例题：“大学老师都是知识分子，有的知识分子有怪脾气，所以有的大学老师有怪脾气”是否正确?

5.定义一个图$G$的补集$Gc$，是把原图上存在的边都断开，不存在的边都连上，顶点不动。求证原图$G$不连通时，$Gc$肯定连通。

### 1.1.2 计算机体系结构(计算机系统结构)

1.RISC布拉布拉

①介绍一下RISC基本特征

②为啥VILW没火起来?

2.介绍了四种分支预测技术，其中为真的时候转移的比例为60%，CPU的CPI为1，分支指令占比20%

①啥都不做，正常流水，分支指令平均延迟3个周期

②总是预测转移条件为真(预测“成功”)，没预测对的时候要延迟1个周期

③总是预测转移条件为假(预测“失败”)，没预测对的时候要延迟1个周期

④动态分支预测技术，分支指令平均0.5个周期

求哪种方案最优?

3.一个CPU有多个处理器核心，当访问数据都在本地cache时要用3个周期，访问一个远程数据要多花1个周期，有100条指令，CPI为2，频率为100$MHz$，求访问的数据都在本地的情况下比有20%的数据在远程cache时要快多少?

4.类似某年408真题，int一个四字节，cache一行32B，总共16KB。
~~~
struct abc{

int a；

int b；

char c；

char d；

}rec[64][64]；

~~~

题目没说行优先存储还是列优先。给了三个双重循环。求各自写缺失(写不命中)率。  
①
~~~
for(int a = 0；a≤ 64；a++)

{

for(int b = 0；b≤ 64；b++)

{

rec[a][b].a++；

rec[a] [b].b++；

rec[a] [b].c++；

rec[a] [b].d++；

}

}
~~~
② 
~~~ 
for(int b = 0；b≤ 64；b++)

{

for(int a = 0；a≤ 64；a++)

{

rec[a] [b].a++；

rec[a] [b].b++；

rec[a] [b].c++；

rec[a] [b].d++；

}

}
~~~
③  
①
 ~~~ 
for(int a = 0；a≤ 64；a++)

{

for(int b = 0；b≤ 64；b++)

{

rec[a] [b].a++；

}

}
~~~
②  
~~~
for(int a = 0；a≤ 64；a++)

{

for(int b = 0；b≤ 64；b++)

{

rec[a] [b].b++；

rec[a] [b].c++；

rec[a] [b].d++；

}

}
~~~
### 1.1.3 编译原理

1.$S→aAb，A→Bb，B→b$(具体文法忘了，大概是这样)

求画出该文法对活前缀aaabb有效的LR(0)项目集。为什么该文法不是SLR文法?

2.线性表示的二叉树文法如下

$ROOT→Btree1 Btree2│NULL$

$Btree→Btree1 Btree2$

$Btree→NULL$

①写一个语法制导定义，求树的深度

②写一个语法制导定义，判断树是否有序(二叉排序树的顺序)

下面已经给出该语法制导定义的部分语句，请补全

$ROOT→Btree1 Btree2│NULL$

~~~
//请在此补全……

if(root.order ==TRUE) print(“ordered!”)；

else print(“not ordered!”)；
~~~

$Btree→Btree1 Btree2$

~~~
//请在此补全……
~~~

$Btree→NULL$
~~~

//请在此补全……其实给的比这多，我记不全了，要你写的就几句
~~~
3.类型表达式

~~~
int \*\*(\*(\*t[19])[20])
~~~

给了各种类型表达式该怎么写，

①写出上面这个怪物的类型表达式

②求t所占的空间大小(假设int和指针都占四字节) 4.基本块与流图 给一段C代码，

①求划分基本块、画出流图

②求出流图各顶点的支配集来画出对应的支配树4.所占的空间大小(假设int和指针都占四字节)

基本块与流图 给一段C代码， ①求划分基本块、画出流图
②求出流图各顶点的支配集来画出对应的支配树

### 1.1.4 数据库

1.基础概念选择题x5

难度类似于以下哪个是灰太狼的儿子?

A.小灰灰 B.吸氧羊 C.懒羊羊 D.慢羊羊

2.基础概念判断题x5

难度类似于 美羊羊是灰太狼的儿子?(X)

3.SQL操作语句x5

给出三个基本表，书上例题原题

~~~
Student(sname，sno(候选码)，sdept)

Courese(cno(候选码)，cname)

选课表SC(sno(候选码)，cno(候选码)，score)
~~~

①查询所有选了数据库的学生学号，姓名

②查询所有姓刘的学生学号、姓名

③查询信息系选了数据库的学生的学号，姓名

④查询选了数据库但没有成绩的学生的学号，姓名

⑤查询平均分在60分以上的学生的学号，姓名

1.2 机试
--------

①判断身份证号是否合法，只验证最后一位校验位。按照给出的方法从前十七位算出校验位，与第十八位对比。

②判断给出的数字能否拆成两个2的幂的和的形式。

比如

$5 = 2^0 + 2^2$

3.给出前缀式，只有加减乘除，求结果。

4.求集合的所有划分，这题很多人都没做出来

如：$\{a，b,c\}$

的划分有

$\{a,b,c\}$

$\{a,\{b,c\}\}$

$\{\{a,b\},c\}$

$\{\{a,c\},b\}$

$\{\{a\},\{b\},\{c\}\}$

特别要求输出格式严格与上述形式一致。

5.给出一个二叉排序树的层次遍历，求从它的一个叶子节点到另外一个叶子节点的路径，要求路径上经过节点的数值之和最大。

2.初试复习
==========

说一下公共课复习，大概成绩是

70 70 130 120

2.1 政治
--------

不要过于重视政治，科大CS复试不算政治，政治分数越高越吃亏，政治只要能过线就行了。

开始是八月，快速听了一遍文都几个老师的讲座，不用要求学会或者学懂，对政治有个大体了解就足够了。

然后慢慢做肖老1000题，摸摸出题的套路。不会的地方就看下肖秀荣全书(没必要做第二遍)。

等风中劲草出来之后仔细阅读小草，认真读两遍。

十一月，政治复习的高潮期才真正开始。

肖八、徐涛八套卷，近三年真题选择题做两遍，一天一套，做到肖四出来为止。

肖八主观题要读懂答题思路，把题目问的知识点写在答案上，通读一遍，不用背。

肖四出来之后，选择题做两遍，整理错题，把选择题错题知识点单独整理。做到能有40分以上为止。

狂背肖四或者徐涛小黄书的大题。

2.2 英语
--------

英语坑在作文上，只能当个反面例子。

刚开始是17年九月，准备的比较早\&\#128514;看语法、单词、长难句。

然后划了快一年水(反面例子一)，直到18年6月才真正开始搞英语。

题型分项：

完型、翻译、新题型我看的是刘晓燕的《两件小事》

阅读理解看的是何凯文。

没必要听他们的视频课，自己做题的手感才是最重要的。

然后是黄皮书，从头到尾做了一遍。

作文是最后才准备的(反面例子二)，王江涛的《20篇》，只背了两遍，最后英语就坑在作文上，还是要多写写多背背。

模拟题少做，但是要精做，张剑的五套卷和朱伟八套卷稍微做下，主要看看作文范文和阅读题的押题。张剑去年押中了一篇原文(GPA和学生毕业那篇)。

背单词要自始至终，但没必要天天背，偶尔背一下，个人推荐百词斩。

2.3 数学
--------

数学是考研重头戏。准备数学开始是17年九月份，用了一个学期看了同济高数上下册，上册的课后例题一个不留全做了。

但是其实没这个必要

18年2月底开始做李永乐全书，用了三个月吧才看完第一遍，不懂的地方再翻翻同济教材。

同步习题和全书例题一定要认真做，搞懂没一个题目。

暑假因为钻研408，数学有点偏废，只做了李永乐的三本辅导讲义和张宇1000题。

九月底开始做的历年真题，一天一张，历年真题做完之后直接开始做模拟题。

当时把李6，张8，张4，汤8，李林4套卷全做了，一天一套，重点就是李林四套卷，这个一定要认真做。

然后还剩点时间，回头研究真题的错题，每个错题都要搞懂。

考前翻翻复习全书，把记不住的公式专门找张纸写下来背背。

2.4 408
-------

408是从7月份开始复习的，之前完全是零基础。

九月底看完第一遍王道(包括题目),然后做了两套408都没及格，发现自己是个弱鸡。

凑巧看到王道的辅导视频，对着视频看了一整遍(看到十月中旬左右看完的，困难章节看了两遍)。

直接在书上认真做了笔记，然后又把书和书上笔记从头看了一遍。

这时候已经十一月了,等真题到了之后，从2018年真题开始从头做了一遍408,标注错题，在选择题上做了笔记。

比上一次试水的时候好太多，已经能拿100分了(虽然还是个弱鸡●)。

然后速看又看了一-遍王道和笔记，用了八天左右。

中间又花了几天时间扫了一下那四本大书，把王道上一笔带过但是真题考过的内容抄在了王道上。

到了十一月20号了，然后做第二遍408(买了一-本201
8年的真题解析备用)，错两次的题目特别标注。

整理了一下错题、真题的笔记，然后做了八套卷的选择题和前两套的大题。

因为实在没时间了，最后就自己写了一个知识大纲，等会拍两张照片发上来。

对着理了一遍知识点，然后又做了一遍八套卷和408的错误选择题(特别是错两遍的,特别在提纲.上标注)。

考前睡了两天，只抽空看了提纲，不记得的又去翻了王道，然后就去考试了。

2.5 一些杂项
------------

### 2.5.1 时间分配：

我一般是八点起床，吃早饭然后赶到自习室，到外面背书到九点，回自习室做数学，然后中午吃饭，睡午觉到1点多，然后下午看408，吃晚饭，晚上回来睡半个小时到七点，搞英语、政治到八点多，然后随机安排数学或者408到11点放学，晚上再吃点夜宵，到寝室之后先翻翻政治，然后继续白天没搞完的数学或者408的错题。

为啥一直睡觉一直吃.。。

人的记忆和睡眠有关的最佳记忆阶段就是睡觉前的前摄记忆和睡醒后的后扰记忆。

吃完饭之后血液会朝胃部流动加大对胃部供氧，这时候强行学习脑袋肯定昏昏沉沉，对消化也不好，不如先睡一觉，消化休息一举两得。

### 2.5.2 关于经验贴：

失败经验比成功经验更重要，很多成功经验贴都很少说心态调整的事，很多失败经验贴倒是会说自己是怎么胡思乱想被心态打败的。

在还有时间富裕的时候可以看看失败经验贴，看看这些前辈当时的心态，想想自己到时候该怎么处理。



3.1 笔试
--------

离散数学、数据库概论、计算机体系结构、编译原理

### 3.1.1 离散数学

先啃方世昌的书两遍，例题再搞懂就足够了，没那么难

最重要的就是群论部分和图论部分的定理证明，看懂思路。

### 3.1.2 数据库系统

推荐看考试点的那个视频，快速过一遍，然后看王珊老师的PPT，两遍就差不多，基础概念要搞懂。

SQL操作那一章节是最重要的，书上例题跟着写写就行了。

### 3.1.3 计算机体系结构

直接看计算机体系机构学习指导那本书，看上两遍，计算公式要搞懂。

### 3.1.4 编译原理

这是最难啃的，科大也推荐了两本参考书，可见课程难度之大。

先对着陈教授的视频啃一遍书，重点是前六章节。

然后再整一遍，把概念搞懂，不同于其他三科，编译原理最好就题型复习。

①正规式和DFA化简

②文法类型判断

③文法项目集

④语法制导定义和翻译方案书写

⑤类型表达式和类型检查的书写

⑥栈式空间分配和静态链、动态链、访问链

⑦基本块划分、流图的支配、dfs树、自然循环

把这几个搞懂就没大问题了。

3.2 机试：
----------

推荐《算法笔记》，跟着把历年真题做一遍，不懂得算法死记硬背也要背下来。

每年固定有一题左右是默写树或者图的算法，一题“跟我学”形式的模拟。

3.3 面试：
----------

准备一个自我介绍，稍微看看408的书。

### 3.3.1 A组面试

**英语交流**，先自我介绍，然后老师和你聊天，问问你喜欢看啥书之类的。

**中文聊天**，问你哪里人，家里几口人。别害羞就行了。

### 3.3.2 B组专业面试

会问一些专业问题，一定会被怼，心态要好，脸皮要厚。

老师：怎么给安徽省五十万高考考生排序，然后查询排名?

我：样本量够大，用外部排序加上K路归并算法

老师：你觉得现在电脑计算能力还是书上说的那种吗，五十万人才多少数据量，我们直接用counting
sort，一遍扫描就行，小伙子，你答的很自信，但是要谦虚啊……

3.4 最后，关于报考
------------------

科大学硕和专硕在一起排名一起录取，前十名左右学硕，后面全专硕。

调剂方向有软院、计院软工(非全)、大数据学院、网络安全学院，放心复习放心考试。
