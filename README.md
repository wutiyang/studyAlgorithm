# studyAlgorithm
## 算法学习
1. 利用Go语言对基础算法进行全面的学习和巩固，以帮助自己以及大家学习数据结构和算法
## 数据结构
* 数组
+ 数组具有随机访问的特性，因为数组是一组连续分配的内存空间所以，它可以通过下标来进行随机访问
+ 数组为什么从零开始
    + 从性能上讲，数组的访问是访问地址的偏移量，如果从1开始，需要减去1才是偏移量，为了性能从0开始
    + 从历史上讲，第一个人使用了0后人沿用
* 链表
    + 是不连续的内存空间，相比数据它的修改（增删改）时间复杂度O(1)，但是空间复杂度是翻倍的，单链表是一倍，双链表是两倍
* 栈
    + 后进先出的数据结构，只有出栈和入栈两个操作
    + 栈的应用
        1. 函数栈，函数调用是嵌套的，函数内先执行，所以要用栈的结构
        2. 运算优先级栈，使用两个栈，一个栈直接存数字，另一个栈存运算符，如果入栈的运算符优先级大于或者等于栈顶，从数字
        栈中取两个数字进行运算，在存入数字栈中，以此递推
        3. 判断字符串是否构成封闭对称的结构，以(){}[]这种简单结构为例，从字符串左边依次进行遍历，当有(直接压入栈中，当遇到)
        在栈中查找与之匹配的符号，出栈并将其他符号再次压入栈中，如果栈中最后没有剩余符号表示，括号匹配，如果有剩余说明，括号不匹配
        4. 实现浏览器前进和后退，访问时入栈1，回退时吧1从栈顶依次压入栈2，类似于倒水，从A杯子倒入B杯子
* 堆
* 队列
* 散列表
* 二叉树
* 跳表
* 图
* Trie树
## 算法
* 递归：f(n)=f(l)+f(r) 利用递推公式 考虑下极限情况即可
* 排序：从下面三个方面去衡量算法的好坏

    ![image](https://github.com/xiangdong1987/studyAlgorithm/blob/master/images/sort.png)
    1. 最好情况，最坏情况，平均情况时间复杂度
    2. 时间复杂度的系数，常数，低阶
    3. 比较次数和移动次数

    重要的概念：
    * 原地排序：是否借助了额外的空间进行
    * 稳定性：排序是否会改变，相同的元素在比较排序的过程中顺序是否会改变
        + 比如：2，9，3，4，8，3  排序后是 2，3，3，4，8，9 如果排序前和排序后两个3的前后顺序没有改变，此算法为稳定排序，反之非稳定排序、
    * 有序度：有序元素对：a[i] <= a[j], 如果 i < j。
    * 满有序度： n*(n-1)/2
    * 逆序度：逆序元素对：a[i] > a[j], 如果 i < j。
    * 交换次数=满序度-逆序度

    归并排序和快速排序思路理解
    * 两个排序都是采取分治的思路，归并利用了先分后治，快速排序是先治后分的方式
    * 归并排序 空间复杂度 O(n) 时间复杂度 O(nlgn) 并稳定的排序算法  不是原地算法
    * 快速排序 空间复杂度 O(1) 时间复杂度 O(nlgn) 并不是稳定的排序算法 是原地算法

    总结：如何实现一个通用的排序算法，Glibc 中的 qsort()就是经典案例，在数据量较小的情况下，使用归并排序就行排序，虽然占用空间，但是以空间换时间，在
    数据量不大情况下成本并不大，但当数据量达到一定值，换成快速排序，但是快速排序也有缺点，如果使用选分界值，只拿第一个如果频繁遇到最最情况，影响效率所
    以可以优化成，三值取中值，或者随机的方式来优化，同时，当数据被分到还有3-4个数据时，可以退化到插入排序，因为当数据量过小时，O(n)和O(lgn)的时间复杂
    度已经非常接近了，所以不需要再调用递归了，增加递归的深度。并且快排是递归排序，会产生递归栈太深造成栈溢出，处理这种方式可以采取限制递归深度，或者做
    一个调用栈函数，手动实现递归的出栈和入栈。
* 二分搜索
* 哈希算法
* 贪心算法
* 分治算法
* 回溯算法
* 动态规划
* 字符串匹配算法
## 目录
### 排序算法
* [冒泡排序](https://github.com/xiangdong1987/studyAlgorithm/tree/master/algorithm/bubbleSort "快速排序")
* [插入排序](https://github.com/xiangdong1987/studyAlgorithm/tree/master/algorithm/insertSort "快速排序")
* [选择排序](https://github.com/xiangdong1987/studyAlgorithm/tree/master/algorithm/selectSort "选择排序")
* [快速排序](https://github.com/xiangdong1987/studyAlgorithm/tree/master/algorithm/quickSort "快速排序")
* [堆排序](https://github.com/xiangdong1987/studyAlgorithm/tree/master/algorithm/heapkSort "堆排序")
* [归并排序](https://github.com/xiangdong1987/studyAlgorithm/tree/master/algorithm/mergeSort "归并排序")
* [计数排序](https://github.com/xiangdong1987/studyAlgorithm/tree/master/algorithm/countSort "计数排序")
* [基数排序](https://github.com/xiangdong1987/studyAlgorithm/tree/master/algorithm/radixSort "基数排序")
### 数据结构
* [树相关](https://github.com/xiangdong1987/studyAlgorithm/tree/master/dataStructure/tree "树相关")