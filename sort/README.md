# 排序算法总结与实现

[TOC]

## 冒泡排序(bubbleSort)

* 介绍
  * 按照规定的方式重复比较相邻的元素, 移动它们的位置. 
* 步骤
  * 比较相邻的元素. 如果第一个比第二个大, 就交换它们的位置(从小到大). 从大到小正好相反.
  * 对0到n-1个数据做同样的工作. 这时, 最大的数就沉到了数组最后的位置上.
  * 针对所有的元素重复以上步骤, 已经排好序的可以不参与操作(忽略最后面沉下去的元素)
* [实现](https://github.com/KuangPanda/Data-structure-and-algorithm-practice/blob/master/sort/bubbleSort.cpp)
* 优化
  * 如果某一次遍历过程中没有发生数据交换, 说明已经是有序的.
  * 记录某次遍历时最后发生数据交换的位置, 这个位置之后的数据已经是有序的
* 复杂度
  * 平均时间: O(n^2)
  * 最坏时间: O(n^2)
  * 空间复杂度: O(1)
  * 稳定性: 稳定




## 选择排序(selectSort)

* 介绍
  * 最直观简单的排序.
* 步骤
  * 在未排序的序列中找到最小(大)元素, 存放在排序序列的起始位置.
  * 再从剩余未排序元素中继续寻找最小(大)元素, 然后放在已排序序列的末尾.
  * 重复上述步骤.
* [实现](https://github.com/KuangPanda/Data-structure-and-algorithm-practice/blob/master/sort/selectSort.cpp)
* 复杂度
  * 平均时间: O(n^2)
  * 最坏时间: O(n^2)
  * 空间复杂度: O(1)
  * 稳定性: 不稳定




## 插入排序(insertSort)

* 介绍

  * 对于未排序的数据, 在已排序序列中从后往前扫描, 找到相应位置并插入.

* 步骤

  ![insertion-sort](./insertion-sort.gif)

  * 从第二个元素开始, 第一个元素认为是有序的
  * 取出下一个元素, 在已经排好序的序列中从后往前扫描
  * 如果被扫描的元素(已排序)大于新的元素, 则前进. 直到找到比新元素值小得元素
  * 将新元素插到该元素的后面

* [实现](https://github.com/KuangPanda/Data-structure-and-algorithm-practice/blob/master/sort/insertSort.cpp)

* 复杂度
  * 平均时间: O(n^2)
  * 最坏时间: O(n^2)
  * 空间复杂度: O(1)
  * 稳定性: 稳定



## 快速排序

* 介绍
  * 快速排序通常明显比同为O(n * logn)的其他算法速度快. 快排采用的思想是分治.
* 步骤
  * 先从数列中取出一个数作为基准数
  * 分区过程, 将比这个数大的元素放在这个数的右边, 将比这个数小的元素放在这个数的左边
  * 分区过程, 先从后往前找, 找到第一个比基准元素小的元素. 在从前往后找, 找到第一个比基准元素大的元素
  * 再对左右区间重复分区过程, 直到各区间只有一个数
* [实现](https://github.com/KuangPanda/Data-structure-and-algorithm-practice/blob/master/sort/quickSort.cpp)
* 复杂度
  * 平均时间: O(nlogn)
  * 最坏时间: O(n^2)
  * 空间复杂度: O(logn ~ n)
  * 稳定性: 不稳定



## 希尔排序

* 介绍
  * 递减增量排序算法, 实质是分组插入排序
* 步骤
  * 先将整个待排元素序列分割成若干个子序列(由相隔某个增量的元素组成的)分别进行直接插入排序, 然后依次缩减增量再进行排序, 待整个序列中的元素基本有序(增量足够小)时, 再对全体元素进行一次直接插入排序
* [实现](https://github.com/KuangPanda/Data-structure-and-algorithm-practice/blob/master/sort/shellSort.cpp)
* 复杂度
  * 平均时间: O(nlogn)
  * 最坏时间: O(n^2)
  * 空间复杂度: O(1)
  * 稳定性: 不稳定



## 归并排序

* 介绍

  * 采用的是分治法, 归并排序的思想就是先递归地分解数组, 再合并数组. 

* 步骤

  ![merge-sort](./merge-sort.gif)

  * 合并有序数组
  * 递归分解数组

* [实现](https://github.com/KuangPanda/Data-structure-and-algorithm-practice/blob/master/sort/mergeSort.cpp)

* 复杂度
  * 平均时间: O(nlogn)
  * 最坏时间: O(nlogn)
  * 空间复杂度: O(1)
  * 稳定性: 稳定

## 基数排序

* 介绍: 
  * **LSD(Least significance digit)**: 短的关键字被认为是小的, 排在前面. 然后相同长度的关键字再按照词典顺序或者数字大小进行排序
  * **MSD(most significance digit)**: 直接按照字典的顺序进行排序, 对于字符串, 单词或者是长度固定的整数排序比较合适
* 步骤
  * 根据整数的最右边数字将其扔进相应的0~9号篮子里, 对于相同的数字要保持其原来的相对顺序(确保算法的稳定性), 然后将篮子里的数串起来, 然后再进行第二趟收集(按照第二位收集), 不断重复当没有更多的位时串起来的数字就是排好序的数字
* [实现]()
* 复杂度
  * 平均时间:
  * 最坏时间:
  * 空间复杂度:
  * 稳定性:

## 堆排序

* 介绍
* 步骤
* [实现]()
* 复杂度
  * 平均时间:
  * 最坏时间:
  * 空间复杂度:
  * 稳定性:

## 桶排序

* 介绍
* 步骤
* [实现]()
* 复杂度
  * 平均时间:
  * 最坏时间:
  * 空间复杂度:
  * 稳定性:




