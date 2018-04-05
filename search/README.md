### 基础

* 查找

  根据给定的某个值, 在查找表中确定一个其关键字等于给定值的数据元素

* 分类

  1. 静态查找和动态查找

     静态或者动态查找都是针对查找表而言的. 动态表是指查找表中有删除和插入操作的表

  2. 有序查找和无序查找

     有序查找是指被查找数列必须为有序数列, 而无序查找对查找数列没有要求, 即有序无序都可以

* 平均查找长度

  1. $$n$$是结点的个数
  2. $$p_i$$是查找第$$i$$个结点的概率, 若不特别申明, 认为每个节点的查找概率相等. $$p_1 = p_2 = ... p_n= 1/n$$
  3. $$c_i$$是找到第$$i$$个结点需要进行比较的次数

  $$
  ASL = \sum_0^n p_i c_i
  $$



### 顺序查找

> 顺序查找适合于存储结构为顺序存储或链式存储的线性表

* 思路

  ​        顺序查找属于无序查找, 从数据结构线性表的一端开始, 顺序查找, 依次将扫描到的结点的关键字与给定值K相比较, 若相等则表示查找成功. 若扫描结束仍没有找到关键字等于k的结点, 表示查找失败 

* 平均查找长度

  $$ ASL = (n + 1) / 2 $$

   



### 二分查找

* 思路

  ​       假设表中的元素是按升序排列, 将表中间位置记录的关键字与查找的关键字进行比较, 如果两者相等, 则查找成功. 否则利用中间位置记录将表分成前后两个子表, 如果中间位置记录的关键字大于查找的关键字, 则进一步查找前一子表, 否则进一步查找后一子表. 重复以上过程, 直到找到满足条件的记录, 使查找成功. 或者到子表不存在为止, 此时查找不成功.

* 要求

  ​       折半查找的优点是比较次数少, 查找速度快, 平均性能好. 其缺点是要求待查表为有序表. 折半法适用于不经常变动而查找频繁的有序列表

* 步骤

  1. 首先, 确定整个查找区间的中间位置**mid = (left + right) / 2**
  2. 用待查关键字值与中间位置的关键字值进行比较
     1. 若想等, 则查找成功
     2. 若大于, 则在后半区域继续进行折半查找, **left = mid + 1**
     3. 若小于, 则在前半区域继续进行折半查找, **right = mid - 1**
  3. 对确定的缩小区域再按折半公式, 重复上面的步骤

* 平均查找长度

  $$ASL = O(log_2 n)$$



### 插值查找

* 思路

  插值查找可以看做是自适应调整移动系数的二分查找算法

  二分查找: $$mid = left + 1/2*(right - left)$$

  插值查找: $$ mid = left + (value - array[left]) / (array[right] - array[left]) * (right - left) $$

  将二分查找的比例系数由$$1/2$$改成了自适应的比例系数


* 要求

  数据不仅是排好序的, 而且呈现均匀分布



### 分块查找

> 分块查找又称索引顺序查找, 是顺序查找的一种改进

* 思路

  ​        将$$n$$个数据元素"按块有序"划分为$$m$$块($$m<=n$$). 每一块中的结点不必有序, 但块与块之间必须"按块有序", 即第一块中的任一元素的关键字都必须小于第二块中任一元素的关键字, 而第二块中的任一元素的关键字必须小于第三块中的任一元素, ......

* 步骤

  1. 先取各块中的最大关键字构成一个索引表
  2. 查找分成两部分, 先对索引表进行二分查找或顺序查找, 以确定待查记录在哪一块. 然后, 在已经确定的块中用顺序法进行查找



### 哈希查找
