---
title: Python：快速排序
date: 2017-08-29 15:16:10
tags: [python]
description: 快速排序：空间复杂度为O（log n），时间复杂度为[O（nlogn）, O(n^2)]，算法不稳定，不具有适应性
categories: Python
keywords: Python

---
# 快速排序
> 空间复杂度为O（log n），时间复杂度为[O（n log n）, O(n^2)]，算法不稳定，不具有适应性

# 基本思想
- 选择基准数（通常为第一个）
- 划分，比基准数大的放基准数右边，小的放左边
- 递归，重复第二步操作，直到基准数的左边和右边分别只剩一个数

# 算法
```
def QuickSort(lst, low, high):
    if low > high:
        return
    l, h = low, high
    temp = lst[l] #取第一个元素为基准数
    while l < h:
        #数组右端扫描
        #把比基准数大的放基准数右边，小的放左边
        #扫描右边，直到右边的数比基准数小
        while l<h and temp <= lst[h]:
            h -= 1
        #将扫描到右边的比基准数小的数放到左边，并将数组左边的下下标加一
        if l < h:
            lst[l] = lst[h]
            l += 1
        #然后从数组的左边进行扫描，直到左边的数比基准数大
        while l < h and temp >= lst[l]:
            l += 1
        #从左边扫描到比基准数大的数放到数组的右边，并将右边数组的下标减一
        if l < h:
            lst[h] = lst[l]
            h -= 1
    lst[l] = temp
    QuickSort(lst, low , l-1)
    QuickSort(lst, h+1, high)
```