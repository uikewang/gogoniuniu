# 算法

#### 常见算法有哪些

排序算法是一类用于将一组数据按照一定顺序重新排列的算法。根据不同的排序方式和性能特点，可以将排序算法分为多种不同类型。以下是一些常见的排序算法：

1. **冒泡排序（Bubble Sort）**：
   - 比较相邻的元素，如果顺序错误则交换它们，直到没有交换操作为止。
   - 时间复杂度：O(n^2)
   - 稳定排序算法
2. **选择排序（Selection Sort）**：
   - 选择最小（或最大）的元素，将其放在数组的起始位置，然后继续选择剩余元素中的最小（或最大）值，依次类推。
   - 时间复杂度：O(n^2)
   - 不稳定排序算法
3. **插入排序（Insertion Sort）**：
   - 将未排序的元素一个一个插入到已排序的部分，依次构建有序序列。
   - 时间复杂度：O(n^2)
   - 稳定排序算法
4. **快速排序（Quick Sort）**：
   - 选择一个基准元素，将数组分为两部分，小于基准的元素放在左边，大于基准的元素放在右边，然后递归地对左右子数组进行排序。
   - 平均时间复杂度：O(n log n)
   - 不稳定排序算法
5. **归并排序（Merge Sort）**：
   - 将数组分成两个子数组，分别对子数组进行排序，然后将排好序的子数组合并成一个有序数组。
   - 时间复杂度：O(n log n)
   - 稳定排序算法
6. **堆排序（Heap Sort）**：
   - 构建一个最大堆或最小堆，然后不断从堆顶取出元素，直到堆为空。
   - 时间复杂度：O(n log n)
   - 不稳定排序算法

每种排序算法都有其适用的场景和性能特点，选择合适的排序算法取决于数据规模、数据分布以及对性能的要求。在实际应用中，通常需要综合考虑这些因素来选择合适的排序算法。

#### 说一下二叉查询：

​			二叉搜索树（Binary Search Tree，BST）是一种常用的二叉树数据结构，它具有以下特点：

1. **结构定义**：二叉搜索树是一棵二叉树，其中每个节点最多有两个子节点，左子树的所有节点的值都小于根节点的值，右子树的所有节点的值都大于根节点的值。这个性质保证了树的左子树上的节点值小于根节点，右子树上的节点值大于根节点，使得树的节点有序排列。
2. **搜索操作**：由于有序性质，二叉搜索树非常适合进行搜索操作。搜索一个特定值时，可以从根节点开始，根据比较结果选择左子树或右子树，依次向下搜索，直到找到目标值或到达叶子节点为止。
3. **插入操作**：插入一个新节点时，首先进行搜索操作找到合适的位置，然后将新节点插入到相应的位置，保持树的有序性质。
4. **删除操作**：删除一个节点时，需要考虑三种情况：
   - 如果节点是叶子节点，直接删除它。
   - 如果节点有一个子节点，将子节点替代被删除节点。
   - 如果节点有两个子节点，找到节点的后继节点（通常是右子树中的最小值节点），将后继节点的值复制到当前节点，然后删除后继节点。
5. **遍历操作**：二叉搜索树支持三种主要的遍历方式，包括前序遍历、中序遍历和后序遍历。其中，中序遍历会按照升序顺序访问树的所有节点，因此可以用来对树进行排序。

尽管二叉搜索树具有很多优点，如快速的搜索和排序能力，但它的性能高度依赖于树的结构。如果树的结构不平衡，即树高度过大，它的性能可能会退化为O(n)，其中n是节点数。为了解决这个问题，人们发展了平衡二叉搜索树，如AVL树和红黑树，以确保树的高度始终保持在可接受的范围内，从而保持高效的性能。

总之，二叉搜索树是一种基本的数据结构，用于实现有序的数据存储、搜索和排序。了解它的基本概念和操作对于理解更高级的树结构和算法非常重要。

#### B+树：

B+树是在B树的基础上进行优化的，使其更适合外存储索引结构，B+树的非叶子结点并不存储数据，而是只存储指针，这样1、B+树磁盘读写代价更低，2、查询效率上B+更高，因为它可以通过顺序访问所有叶子节点来获取数据，而B-树只能通过查找操作来获取数据。3、因为B+树是双向指针进行连接的，所以B+树更便于扫库和区间查询

#### （不重要）B树和二叉搜索树的区别：

B树（B-tree）和二叉搜索树（Binary Search Tree，BST）是两种不同的数据结构，它们有一些相似之处，但也存在重要的区别。它们都用于存储和组织数据，但用途和结构不同。

以下是它们之间的主要区别：

1. **多路平衡树 vs 二叉树**:
   - B树是一种多路平衡查找树，每个节点可以包含多个子节点（通常是大于2的子节点），而不仅仅是两个。这使得B树更适合于存储和管理大量数据，特别是在磁盘上。
   - 二叉搜索树是一种每个节点最多有两个子节点的树结构。
2. **平衡性**:
   - B树是一种自平衡树，通过维护平衡性质，保持树的高度相对较小。这使得B树在大规模数据存储中的插入、删除和查找操作具有稳定的性能。
   - 二叉搜索树不一定是平衡的，其性能在最坏情况下可能会退化为O(n)，其中n是节点数量。为了解决这个问题，出现了平衡二叉搜索树，如AVL树和红黑树。
3. **查找操作**:
   - B树的查找操作不仅能够进行精确查找，还支持范围查找，因为它的节点有序。
   - 二叉搜索树主要用于精确查找，范围查找需要进行额外的处理。
4. **用途**:
   - B树通常用于文件系统、数据库索引等需要高效地处理大量数据的场景。
   - 二叉搜索树通常用于一般性的数据存储和查找，以及在内存中进行数据排序。

总之，B树和二叉搜索树虽然都是树状数据结构，但它们在结构、性能和用途上有显著不同。B树适用于大规模数据的存储和检索，而二叉搜索树通常用于一般性的数据操作。在实际应用中，选择合适的数据结构取决于数据量和操作的需求。

#### 红黑树

##### 红黑树你知道吗？

红黑树是由AVL树发展来的，也相当于是AVL树的进化版，AVL树是任何一个节点左子支高度与右子支高度之差的绝对值不超过1，这个规定太死了，实现起来困难，所以就出现红黑树，红黑树的节点是红色或黑色的，根是黑色的，所有的叶子都是黑色的	，每个红色节点必须有两个黑节点，红色节点不能连续，从任一节点到其每个叶子的所有简单路径都包含相同数目的黑色节点；红黑树的基本操作与其他树差不多，都包括查找、增加、删除等操作，在进行这些操作的同时还要保存红黑树的规则，则就需要用到旋转操作、调色、调位操作等，旋转操作分为左旋和右旋，左旋是将某个节点旋转为其右孩子的左孩子，而右旋是节点旋转为其左孩子的右孩子

![1693907217103](D:/Program file/typora/img/1693907217103.png)

##### 为什么在解决 hash 冲突的时候，不直接用红黑树？而选择先用链表，再转红黑树?

因为红黑树需要进行左旋，右旋，变色这些操作来保持平衡，而单链表不需要。当元素小于 8 个的时候，此时做查询操作，链表结构已经能保证查询性能。当元素大于 8 个的时候， 红黑树搜索时间复杂度是 O(logn)，而链表是 O(n)，此时需要红黑树来加快查询速度，但是新增节点的效率变慢了。

因此，如果一开始就用红黑树结构，元素太少，新增效率又比较慢，无疑这是浪费性能的。