[](https://oiwiki.org/edit-landing/?ref=/graph/virtual-tree.md "编辑此页")

## 虚树

## 引入[](#引入 "Permanent link")

[「SDOI2011」消耗战](https://www.luogu.com.cn/problem/P2495)

**题目描述**

在一场战争中，战场由 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "n") 个岛屿和 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "n-1") 个桥梁组成，保证每两个岛屿间有且仅有一条路径可达。现在，我军已经侦查到敌军的总部在编号为 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1") 的岛屿，而且他们已经没有足够多的能源维系战斗，我军胜利在望。已知在其他 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "k") 个岛屿上有丰富能源，为了防止敌军获取能源，我军的任务是炸毁一些桥梁，使得敌军不能到达任何能源丰富的岛屿。由于不同桥梁的材质和结构不同，所以炸毁不同的桥梁有不同的代价，我军希望在满足目标的同时使得总代价最小。

侦查部门还发现，敌军有一台神秘机器。即使我军切断所有能源之后，他们也可以用那台机器。机器产生的效果不仅仅会修复所有我军炸毁的桥梁，而且会重新随机资源分布（但可以保证的是，资源不会分布到 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1") 号岛屿上）。不过侦查部门还发现了这台机器只能够使用 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "m") 次，所以我们只需要把每次任务完成即可。

**输入格式**

第一行一个整数 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "n")，代表岛屿数量。

接下来 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "n-1") 行，每行三个整数 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "u,v,w")，代表 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "u") 号岛屿和 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "v") 号岛屿由一条代价为 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "w") 的桥梁直接相连，保证 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1\le u,v\le n") 且 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1\le w\le 10^5")。

第 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "n+1") 行，一个整数 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "m")，代表敌方机器能使用的次数。

接下来 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "m") 行，每行一个整数 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "k_i")，代表第 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "i") 次后，有 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "k_i") 个岛屿资源丰富，接下来 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "k") 个整数 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "h_1,h_2,\cdots ,h_k")，表示资源丰富岛屿的编号。

**输出格式**

输出有 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "m") 行，分别代表每次任务的最小代价。

**数据范围**

对于 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "100\%") 的数据，![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "2\le n\le 2.5\times 10^5,1\le m\le 5\times 10^5,\sum k_i\le 5\times 10^5,1\le k_i\le n-1")。

### 朴素做法[](#朴素做法 "Permanent link")

对于上面那题，我们不难发现——如果树的点数很少，那么我们可以直接跑 DP。

首先我们称某次询问中被选中的点为——**「关键点」**。

设 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "Dp(i)") 表示——使 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "i") 不与其子树中任意一个关键点连通的 **最小代价**。

设 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "w(a,b)") 表示 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "a") 与 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "b") 之间的边的权值。

则枚举 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "i") 的儿子 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "v")：

很好，这样我们得到了一份 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "O(nq)") 的代码。

听起来很有意思。

### 优化做法[](#优化做法 "Permanent link")

我们不难发现——其实很多点是没有用的。以下图为例：

![vtree-1](https://oiwiki.org/graph/images/vtree-tree.svg)

如果我们选取的关键点是：

![vtree-2](https://oiwiki.org/graph/images/vtree-key-vertex.svg)

图中只有两个红色的点是 **关键点**，而别的点全都是「非关键点」。

对于这题来说，我们只需要保证红色的点无法到达 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1") 号节点就行了。

通过肉眼观察可以得出结论——![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1") 号节点的右子树（虽然实际上可能有多个子树，但这里只有两个子树，所以暂时这么称呼了）一个红色节点都没有，**所以没必要去 DP 它**。

观察题目给出的条件，红色点（关键点）的总数是与 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "n") 同阶的，也就是说实际上一次询问中红色的点对于整棵树来说是很稀疏的，所以如果我们能让复杂度由红色点的总数来决定就好了。

因此我们需要 **浓缩信息，把一整颗大树浓缩成一颗小树**。

## 虚树 Virtual Tree[](#虚树-virtual-tree "Permanent link")

由此我们引出了 **「虚树」** 这个概念。

我们先直观地来看看虚树的样子。

下图中，红色结点是我们选择的关键点。红色和黑色结点都是虚树中的点。黑色的边是虚树中的边。

![vtree-3](https://oiwiki.org/graph/images/vtree-vtree1.svg)

![vtree-4](https://oiwiki.org/graph/images/vtree-vtree2.svg)

![vtree-5](https://oiwiki.org/graph/images/vtree-vtree3.svg)

![vtree-6](https://oiwiki.org/graph/images/vtree-vtree4.svg)

因为任意两个关键点的 LCA 也是需要保存重要信息的，所以我们需要保存它们的 LCA，因此虚树中不一定只有关键点。

不难发现虚树中祖先后代的关系并不会改变。（就是不会出现原本 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "a") 是 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "b") 的祖先结果后面 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "a") 变成 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "b") 的后代了之类的鬼事）

但我们不可能 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "O(k^2)") 暴力枚举 LCA，所以我们不难想到——首先将关键点按 DFS 序排序，然后排完序以后相邻的两个关键点（相邻指的是在排序后的序列中下标差值的绝对值等于 1）求一下 LCA，并把它加入虚树。

我们的当务之急就是如何构造虚树。

在提出方案之前，我们先确认一个事实——在虚树里，只要保证祖先后代的关系没有改变，就可以随意添加节点。

也就是，如果我们乐意，我们可以把原树中所有的点都加入虚树中，也不会导致 WA（虽然会导致 TLE）。

因此，我们为了方便，可以首先将 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1") 号节点加入虚树中，并且并不会影响答案。

### 第一种构造过程：二次排序 + LCA 连边[](#第一种构造过程二次排序--lca-连边 "Permanent link")

因为多个节点的 LCA 可能是同一个，所以我们不能多次将它加入虚树。

非常直观的一个方法是：

+   将关键点按 DFS 序排序；
+   遍历一遍，任意两个相邻的关键点求一下 LCA，并且判重；
+   然后根据原树中的祖先后代关系建树。

具体实现上，在 **关键点序列** 上，枚举 **相邻的两个数**，两两求得 LCA 并且加入序列 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "A") 中。

因为 DFS 序的性质，此时的序列 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "A") 已经包含了 **虚树中的所有点**，但是可能有重复。

所以我们把序列 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "A") 按照 DFS 序 **从小到大排序并去重**。

最后，在序列 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "A") 上，枚举 **相邻** 的两个 **点编号** ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "x,y")，求得它们的 LCA 并且连接 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "\operatorname{LCA}(x,y),y")，虚树就构造完成了。

为什么连接 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "\operatorname{LCA}(x,y)") 和 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y") 可以做到不重不漏呢？

证明

如果 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "x") 是 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y") 的祖先，那么 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "x") 直接到 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y") 连边。因为 DFS 序保证了 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "x") 和 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y") 的 DFS 序是相邻的，所以 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "x") 到 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y") 的路径上面没有关键点。

如果 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "x") 不是 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y") 的祖先，那么就把 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "\operatorname{LCA}(x,y)") 当作 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y") 的的祖先，根据上一种情况也可以证明 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "\operatorname{LCA}(x,y)") 到 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y") 点的路径上不会有关键点。

所以连接 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "\operatorname{LCA}(x,y)") 和 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "y")，不会遗漏，也不会重复。

另外第一个点没有被一个节点连接会不会有影响呢？因为第一个点一定是这棵树的根，所以不会有影响，所以总边数就是 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "m-1") 条。

因为至少要两个实点才能够召唤出来一个虚点，再加上一个根节点，所以虚树的点数就是实点数量的两倍。

时间复杂度 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "O(m\log n)")，其中 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "m") 为关键点数，![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "n") 为总点数。

#### 实现[](#实现 "Permanent link")

<table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal"> 1</span>
<span class="normal"> 2</span>
<span class="normal"> 3</span>
<span class="normal"> 4</span>
<span class="normal"> 5</span>
<span class="normal"> 6</span>
<span class="normal"> 7</span>
<span class="normal"> 8</span>
<span class="normal"> 9</span>
<span class="normal">10</span>
<span class="normal">11</span>
<span class="normal">12</span>
<span class="normal">13</span>
<span class="normal">14</span>
<span class="normal">15</span>
<span class="normal">16</span>
<span class="normal">17</span>
<span class="normal">18</span>
<span class="normal">19</span>
<span class="normal">20</span>
<span class="normal">21</span></pre></div></td><td class="code"><div><pre><span></span><code><span class="kt">int</span><span class="w"> </span><span class="n">dfn</span><span class="p">[</span><span class="n">MAXN</span><span class="p">];</span>
<span class="kt">int</span><span class="w"> </span><span class="n">h</span><span class="p">[</span><span class="n">MAXN</span><span class="p">],</span><span class="w"> </span><span class="n">m</span><span class="p">,</span><span class="w"> </span><span class="n">a</span><span class="p">[</span><span class="n">MAXN</span><span class="p">],</span><span class="w"> </span><span class="n">len</span><span class="p">;</span><span class="w">  </span><span class="c1">// 存储关键点</span>

<span class="kt">bool</span><span class="w"> </span><span class="nf">cmp</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">x</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">y</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">dfn</span><span class="p">[</span><span class="n">x</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">dfn</span><span class="p">[</span><span class="n">y</span><span class="p">];</span><span class="w">  </span><span class="c1">// 按照 dfs 序排序</span>
<span class="p">}</span>

<span class="kt">void</span><span class="w"> </span><span class="nf">build_virtual_tree</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="n">sort</span><span class="p">(</span><span class="n">h</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">h</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">m</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">cmp</span><span class="p">);</span><span class="w">  </span><span class="c1">// 把关键点按照 dfs 序排序</span>
<span class="w">  </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">m</span><span class="p">;</span><span class="w"> </span><span class="o">++</span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="n">a</span><span class="p">[</span><span class="o">++</span><span class="n">len</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">h</span><span class="p">[</span><span class="n">i</span><span class="p">];</span>
<span class="w">    </span><span class="n">a</span><span class="p">[</span><span class="o">++</span><span class="n">len</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">lca</span><span class="p">(</span><span class="n">h</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">h</span><span class="p">[</span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">]);</span><span class="w">  </span><span class="c1">// 插入 lca</span>
<span class="w">  </span><span class="p">}</span>
<span class="w">  </span><span class="n">a</span><span class="p">[</span><span class="o">++</span><span class="n">len</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">h</span><span class="p">[</span><span class="n">m</span><span class="p">];</span>
<span class="w">  </span><span class="n">sort</span><span class="p">(</span><span class="n">a</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">a</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">len</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">cmp</span><span class="p">);</span><span class="w">  </span><span class="c1">// 把所有虚树上的点按照 dfs 序排序</span>
<span class="w">  </span><span class="n">len</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">unique</span><span class="p">(</span><span class="n">a</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">a</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">len</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">a</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span><span class="w">  </span><span class="c1">// 去重</span>
<span class="w">  </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">lc</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">len</span><span class="p">;</span><span class="w"> </span><span class="o">++</span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">    </span><span class="n">lc</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">lca</span><span class="p">(</span><span class="n">a</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">a</span><span class="p">[</span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">]);</span>
<span class="w">    </span><span class="n">conn</span><span class="p">(</span><span class="n">lc</span><span class="p">,</span><span class="w"> </span><span class="n">a</span><span class="p">[</span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">]);</span><span class="w">  </span><span class="c1">// 连边，如有边权 就是 distance(lc,a[i+1])</span>
<span class="w">  </span><span class="p">}</span>
<span class="p">}</span>
</code></pre></div></td></tr></tbody></table>

其实这样就足以构造一棵虚树了。

### 第二种构造过程：使用单调栈[](#第二种构造过程使用单调栈 "Permanent link")

如何使用单调栈构造虚树？

首先我们要明确一个目的——我们要用单调栈来维护一条虚树上的链。

也就是一个栈里相邻的两个节点在虚树上也是相邻的，而且栈是从底部到栈首单调递增的（指的是栈中节点 DFS 序单调递增），说白了就是某个节点的父亲就是栈中它下面的那个节点。

首先我们在栈中添加节点 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "1")。

然后接下来按照 DFS 序从小到大添加关键节点。

假如当前的节点与栈顶节点的 LCA 就是栈顶节点的话，则说明它们是在一条链上的。所以直接把当前节点入栈就行了。

![vtree-7](https://oiwiki.org/graph/images/vtree-add1.svg)

假如当前节点与栈顶节点的 LCA 不是栈顶节点的话：

![vtree-8](https://oiwiki.org/graph/images/vtree-add2.svg)

这时，当前单调栈维护的链是：

![vtree-9](https://oiwiki.org/graph/images/vtree-add3.svg)

而我们需要把链变成：

![vtree-10](https://oiwiki.org/graph/images/vtree-add4.svg)

那么我们就把用虚线标出的结点弹栈即可，在弹栈前别忘了向它在虚树中的父亲连边。

![vtree-11](https://oiwiki.org/graph/images/vtree-add5.svg)

假如弹出以后发现栈首不是 LCA 的话要让 LCA 入栈。

再把当前节点入栈就行了。

下面给出一个具体的例子。假设我们要对下面这棵树的 4，6 和 7 号结点建立虚树：

![vtree-12](https://oiwiki.org/graph/images/vtree-construction1.svg)

那么步骤是这样的：

![vtree-13](https://oiwiki.org/graph/images/vtree-construction2.svg)

我们用红色的点代表在栈内的点，青色的点代表从栈中弹出的点。

![vtree-14](https://oiwiki.org/graph/images/vtree-construction3.svg)

![vtree-15](https://oiwiki.org/graph/images/vtree-construction4.svg)

![vtree-16](https://oiwiki.org/graph/images/vtree-construction5.svg)

![vtree-17](https://oiwiki.org/graph/images/vtree-construction6.svg)

![vtree-18](https://oiwiki.org/graph/images/vtree-construction7.svg)

我们接下来将那些没入过栈的点（非青色的点）删掉，对应的虚树长这个样子：

![vtree-19](https://oiwiki.org/graph/images/vtree-construction8.svg)

其中有很多细节，比如用邻接表存图的方式存虚树的话，需要清空邻接表。但是直接清空整个邻接表是很慢的，所以我们在 **有一个从未入栈的元素入栈的时候清空该元素对应的邻接表** 即可。

#### 实现[](#实现_1 "Permanent link")

建立虚树的 C++ 代码大概长这样：

代码实现

<table class="highlighttable"><tbody><tr><td class="linenos"><div class="linenodiv"><pre><span></span><span class="normal"> 1</span>
<span class="normal"> 2</span>
<span class="normal"> 3</span>
<span class="normal"> 4</span>
<span class="normal"> 5</span>
<span class="normal"> 6</span>
<span class="normal"> 7</span>
<span class="normal"> 8</span>
<span class="normal"> 9</span>
<span class="normal">10</span>
<span class="normal">11</span>
<span class="normal">12</span>
<span class="normal">13</span>
<span class="normal">14</span>
<span class="normal">15</span>
<span class="normal">16</span>
<span class="normal">17</span>
<span class="normal">18</span>
<span class="normal">19</span>
<span class="normal">20</span>
<span class="normal">21</span>
<span class="normal">22</span>
<span class="normal">23</span>
<span class="normal">24</span>
<span class="normal">25</span>
<span class="normal">26</span>
<span class="normal">27</span>
<span class="normal">28</span>
<span class="normal">29</span>
<span class="normal">30</span>
<span class="normal">31</span>
<span class="normal">32</span>
<span class="normal">33</span></pre></div></td><td class="code"><div><pre><span></span><code><span class="kt">bool</span><span class="w"> </span><span class="nf">cmp</span><span class="p">(</span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">x</span><span class="p">,</span><span class="w"> </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">y</span><span class="p">)</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="k">return</span><span class="w"> </span><span class="n">id</span><span class="p">[</span><span class="n">x</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">id</span><span class="p">[</span><span class="n">y</span><span class="p">];</span><span class="w"> </span><span class="p">}</span>

<span class="kt">void</span><span class="w"> </span><span class="nf">build</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<span class="w">  </span><span class="n">sort</span><span class="p">(</span><span class="n">h</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">h</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">k</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">cmp</span><span class="p">);</span>
<span class="w">  </span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">g</span><span class="p">.</span><span class="n">sz</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">g</span><span class="p">.</span><span class="n">head</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">-1</span><span class="p">;</span>
<span class="w">  </span><span class="c1">// 1 号节点入栈，清空 1 号节点对应的邻接表，设置邻接表边数为 1</span>
<span class="w">  </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="n">l</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">k</span><span class="p">;</span><span class="w"> </span><span class="o">++</span><span class="n">i</span><span class="p">)</span>
<span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">h</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<span class="w">      </span><span class="c1">// 如果 1 号节点是关键节点就不要重复添加</span>
<span class="w">      </span><span class="n">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">lca</span><span class="p">(</span><span class="n">h</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="p">]);</span>
<span class="w">      </span><span class="c1">// 计算当前节点与栈顶节点的 LCA</span>
<span class="w">      </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<span class="w">        </span><span class="c1">// 如果 LCA 和栈顶元素不同，则说明当前节点不再当前栈所存的链上</span>
<span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">id</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">id</span><span class="p">[</span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">]])</span>
<span class="w">          </span><span class="c1">// 当次大节点的 Dfs 序大于 LCA 的 Dfs 序</span>
<span class="w">          </span><span class="n">g</span><span class="p">.</span><span class="n">push</span><span class="p">(</span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">],</span><span class="w"> </span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="p">]),</span><span class="w"> </span><span class="n">top</span><span class="o">--</span><span class="p">;</span>
<span class="w">        </span><span class="c1">// 把与当前节点所在的链不重合的链连接掉并且弹出</span>
<span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">id</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">id</span><span class="p">[</span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">]])</span>
<span class="w">          </span><span class="c1">// 如果 LCA 不等于次大节点（这里的大于其实和不等于没有区别）</span>
<span class="w">          </span><span class="n">g</span><span class="p">.</span><span class="n">head</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">-1</span><span class="p">,</span><span class="w"> </span><span class="n">g</span><span class="p">.</span><span class="n">push</span><span class="p">(</span><span class="n">l</span><span class="p">,</span><span class="w"> </span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="p">]),</span><span class="w"> </span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="p">;</span>
<span class="w">        </span><span class="c1">// 说明 LCA 是第一次入栈，清空其邻接表，连边后弹出栈顶元素，并将 LCA</span>
<span class="w">        </span><span class="c1">// 入栈</span>
<span class="w">        </span><span class="k">else</span>
<span class="w">          </span><span class="n">g</span><span class="p">.</span><span class="n">push</span><span class="p">(</span><span class="n">l</span><span class="p">,</span><span class="w"> </span><span class="n">sta</span><span class="p">[</span><span class="n">top</span><span class="o">--</span><span class="p">]);</span>
<span class="w">        </span><span class="c1">// 说明 LCA 就是次大节点，直接弹出栈顶元素</span>
<span class="w">      </span><span class="p">}</span>
<span class="w">      </span><span class="n">g</span><span class="p">.</span><span class="n">head</span><span class="p">[</span><span class="n">h</span><span class="p">[</span><span class="n">i</span><span class="p">]]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">-1</span><span class="p">,</span><span class="w"> </span><span class="n">sta</span><span class="p">[</span><span class="o">++</span><span class="n">top</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">h</span><span class="p">[</span><span class="n">i</span><span class="p">];</span>
<span class="w">      </span><span class="c1">// 当前节点必然是第一次入栈，清空邻接表并入栈</span>
<span class="w">    </span><span class="p">}</span>
<span class="w">  </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">top</span><span class="p">;</span><span class="w"> </span><span class="o">++</span><span class="n">i</span><span class="p">)</span>
<span class="w">    </span><span class="n">g</span><span class="p">.</span><span class="n">push</span><span class="p">(</span><span class="n">sta</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">sta</span><span class="p">[</span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">]);</span><span class="w">  </span><span class="c1">// 剩余的最后一条链连接一下</span>
<span class="w">  </span><span class="k">return</span><span class="p">;</span>
<span class="p">}</span>
</code></pre></div></td></tr></tbody></table>

于是我们就学会了虚树的建立了！

对于消耗战这题，直接在虚树上跑最开始讲的那个 DP 就行了，我们等于利用了虚树排除了那些没用的非关键节点！仍然考虑 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "i") 的所有儿子 ![](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "v")：

于是这题很简单就过了。

## 推荐习题[](#推荐习题 "Permanent link")

+   [「SDOI2011」消耗战](https://www.luogu.com.cn/problem/P2495)
+   [「HEOI2014」大工程](https://www.luogu.com.cn/problem/P4103)
+   [CF613D Kingdom and its Cities](http://codeforces.com/contest/613/problem/D/)
+   [「HNOI2014」世界树](https://www.luogu.com.cn/problem/P3233)

* * *

> 本页面最近更新：2024/10/9 22:38:42，[更新历史](https://github.com/OI-wiki/OI-wiki/commits/master/docs/graph/virtual-tree.md)  
> 发现错误？想一起完善？ [在 GitHub 上编辑此页！](https://oiwiki.org/edit-landing/?ref=/graph/virtual-tree.md "edit.link.title")  
> 本页面贡献者：[konnyakuxzy](https://github.com/konnyakuxzy), [ksyx](https://github.com/ksyx), [greyqz](https://github.com/greyqz), [HeRaNO](https://github.com/HeRaNO), [Ir1d](https://github.com/Ir1d), [SmallTualatin](https://github.com/SmallTualatin), [sshwy](https://github.com/sshwy), [Xeonacid](https://github.com/Xeonacid), [aofall](https://github.com/aofall), [Chiechun](https://github.com/Chiechun), [CoelacanthusHex](https://github.com/CoelacanthusHex), [countercurrent-time](https://github.com/countercurrent-time), [Early0v0](https://github.com/Early0v0), [Enter-tainer](https://github.com/Enter-tainer), [GoodCoder666](https://github.com/GoodCoder666), [H-J-Granger](https://github.com/H-J-Granger), [Henry-ZHR](https://github.com/Henry-ZHR), [HTensor](https://github.com/HTensor), [hyx1124](https://github.com/hyx1124), [iamtwz](https://github.com/iamtwz), [kfy666](https://github.com/kfy666), [Marcythm](https://github.com/Marcythm), [mcendu](https://github.com/mcendu), [megakite](https://github.com/megakite), [mgt](mailto:i@margatroid.xyz), [NachtgeistW](https://github.com/NachtgeistW), [ouuan](https://github.com/ouuan), [Persdre](https://github.com/Persdre), [shiftooo](https://github.com/shiftooo), [shuzhouliu](https://github.com/shuzhouliu), [StudyingFather](https://github.com/StudyingFather), [SukkaW](https://github.com/SukkaW), [szdytom](https://github.com/szdytom), [tder6](https://github.com/tder6), [Tiphereth-A](https://github.com/Tiphereth-A), [tth37](https://github.com/tth37), [william-song-shy](https://github.com/william-song-shy), [yjl9903](https://github.com/yjl9903)  
> 本页面的全部内容在 **[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.zh) 和 [SATA](https://github.com/zTrix/sata-license)** 协议之条款下提供，附加条款亦可能应用