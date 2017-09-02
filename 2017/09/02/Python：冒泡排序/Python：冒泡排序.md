---
title: Python：冒泡排序
date: 2017-09-02 15:48:10
tags: [python]
description: 冒泡排序：空间复杂度为O（1），时间复杂度为O（n^2）,改进算法的时间复杂度最好情况为O(n)，算法稳定，具有适应性
categories: Python
keywords: Python

---
### 冒泡排序
> 空间复杂度为O（1），时间复杂度为O（n^2）,改进算法的时间复杂度最好情况为O(n)，算法稳定，具有适应性


#### 基本思想
> 比较相邻元素，如为逆序，则交换位置

#### 算法
```bash
def bubble_sort(lst):  
    for i in range(len(lst)):  
        for j in range(1, len(lst)-i):
            if lst[j-1] > lst[j]:  
                lst[j-1], lst[j] = lst[j], lst[j-1]  
    print lst
```