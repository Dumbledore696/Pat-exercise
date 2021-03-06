# Pat-exercise
记录刷题代码，菜鸟升级之路
### B1052

字符串操作

* “Are you kidding me? @\/@”的’\’是转义字符，想要输出’\’就要用’\\’表示

* 别忘了加上a<1||b<1||c<1||d<1||e<1

* ```c++
  if(t1[i]==' '||t1[i]=='['||t1[i]==']'){
      i++;
      continue;
  }
  ```
  
  改为
  
  ```c++
  if(t1[i++]!='['){
      continue;
  }
  ```
  
  因为'[]'外的字符不只有空格
  
* 程序改进之处：改用vector<vector <string> > ,不需要用map，用string的substr截取[]中的字符串substr(pos,len)

* 注意格式正确，在Are you kidding me? @\/@ 后输出换行符。

### B1077

* 四舍五入函数round在math.h中，sqrt和pow也在math.h中，max，min在algorithm中
* 四舍五入也可用` printf("%d\n",int(re+0.5));`

### B1070

* 排序加贪心

* ```c++
  for(int i=0;i<n-1;i++){
          double temp=(c[i]+c[i+1])/2;
          c[i+1]=temp;
  }
  ```

  可改成

  ```c++
  int result = v[0];
      for (int i = 1; i < n; i++)
          result = (result + v[i]) / 2;
  ```

* 向下取整用floor()

### B1087

* 利用set的去重性，一开始没想到，想找规律，这条路行不通就模拟从1到n的过程，将生成的结果放到set中
* 复习了set的insert用法
* 向下取整，整数除法自动向下取整

### B1066

* 多重循环中最好用printf，不用cout，防止超时

### B1084

* `memset(a,0,sizeof(a))`头文件cstring
* 注意迭代n-1次
* 我用的是三个vector做的很烦，柳神用两个字符串就解决了，转化为字符串拼接问题

### B1093

* 字符是ASCII码，可直接当作整数用
* 两个字符串可拼接后使用

### B1091

* 阶乘时注意谨慎使用pow()，`int n=pow(5,2)`结果n等于24，换成double即可
* `string c = a.substr(a.length() - b.length());`截取a的后x位，x为b的位数，即看a后几位是否和b相同，可以转化为字符串问题。
* to_string的使用

### B1072

* 输出编号时注意%04d格式
* map用不了find，set有find

### B1050(×)

* vector容器只有在初始化之后才能直接输入

  ```c++
  vector<int> v(10);
  cin>>v[1];
  或
  vector<int> v;
  int temp=10;
  v.push_back(temp);
  ```

* 对二维向量进行初始化，创建一个10*5的二维向量

  ```c++
  vector< vector<int> > b(10, vector<int>(5));
  cin>>b[1][1]
  ```

* 复习了sort中cmp函数的写法

* 找两数(m>=n)相乘等于N，且两数之差最小的算法，N的平方根的整数部分向1递减到第一个能被N整除的数即为n，m=N/n

* 模拟题，分为两个循环，大循环次数为level，小循环有四种，慢慢确定小循环的上下边界

### B1053

* printf 要两个%%才能输出百分号

* 小数除法时，要用double，否则两个整型计算后为0

  如2/5=0，（double）2/5=0.4

### B1054(×) （字符串转数字）

* 转化为字符串操作

* sscanf：从字符串读进指定格式的数据，这一步可以将许多非法数据过滤掉

  sprintf：将数据以指定格式写进字符串

  这里的**字符串为char字符数组**，用%s输入、输出

* 判断用原字符串和%.2f指定格式的字符串进行比较

### B1055(×)

* 结构体排序问题，没想到，容器用错为map，导致无法排序，正解将名字和身高作为一个结构体类型，再用vector来存储结构体类型，对vector进行排序
* 输出时按行输出，两个指针在两个容器中移动，先输出中间，再输出左边，最后输出右边
* 排序时注意先按身高从大到小，再按名字从小到大
* 注意中心位置，题中是m/2+1,是从1开始计的，程序中中心位置为m/2

### B1058 选择题

* 输入比较难，有括号，括号中输入时还要按照第一个数输入下面的数

* 输出防止末尾有多余空格符，输出（ "  %d"）

* scanf中的%d和%c之间一定要有分隔符的主动scanf输入，否则可能接收成空格或者空值

  ```c++
  scanf("(%d ",&num);
  scanf(" %c",&ans_single);
  scanf(")");
  ```

### B1059 C语言竞赛

* 判断是否为素数算法
* map可改为数组

### B1060 爱丁顿数

* 逻辑题，先排序

### A1053 DFS+树+保存路径

* 注意用vector来保存路径时，首先将根节点的权重放到single中。
* 注意先排序

### A1043 二叉排序树

* 涉及二叉排序树的操作，包括插入，建树，先序遍历，后序遍历
* 本题镜像树可以通过翻转树实现，也可通过遍历时反向遍历实现

### A1066 平衡二叉树

* 注意newnode时，将高度置为1，root=NULL时，高度才为0；

* RR和RL型，根节点的平衡因子为-2

* 编写的函数有：

  | newnode          | getheight    | create  |
  | :--------------- | ------------ | ------- |
  | getbalancefactor | updateheight | Rrotate |
  | Lrotate          | insert       |         |

### 并查集

* 编写的函数有

  | initial | find_Father | union |
  | ------- | ----------- | ----- |
  |         |             |       |

### 堆排序

* 建堆：向上执行，向下调整  downadjust、createHeap
* 删除堆顶：向下调整 downAdjust、deleteTop
* 插入数据：向上调整 upAdjust、insert
* 堆排序=建堆+向下调整 createHeap、downAdjust

### A1034 图的DFS

* map实现字符串与图顶点序号的互换
* 注意无向图用邻接矩阵存储，点权值用weight数组存储
* DFS过程中求每个连通分量的边权值总和（先判断能不能到达，加上之后，再将边置为0，再判断点是否访问再DFS下个顶点）、总人数、点权值最大的那个顶点。
* 输出按字母顺序，用map

### A1076 图的BFS

* 注意邻接表结构的指向，由被关注的人指向转发的人

* memset用法，加cstring头文件，`memset(inq,false,sizeof(inq))`

* 注意每次BFS前inq[maxn]要初始化

* 本题为带layer的BFS，`vector<Node> adj[maxn]` 

  `struct Node{int v,int layer};`

### A1003 单源最短路径Dijkstra

* 注意将`G[maxn][maxn]`初始化`fill(G[0],G[0]+maxn*maxn,INF)`
* 求点权最大的最短路径，`w[s]=weight[s],其他的为0`
* 求最短路径的条数 `num[s]=1,其他的为0`

### A1030 Dijkstra+DFS模板

* 注意v.pop_back()，括号中为空
* 用`vector<int> pre[maxn]`通过Dijkstra的求解记录所有最短路径，再用DFS遍历所有最短路径，找出使第二标尺最优的路径

