---
title: Python：归并排序
date: 2017-08-29 15:46:20
tags: [python]
description: 归并排序：空间复杂度为O（log n），时间复杂度为O（nlogn），算法稳定，不具有适应性
categories: Python
keywords: Python 归并排序

---

# Python: 归并排序

> 归并排序算法：空间复杂度为O（n），时间复杂度为O（nlogn），算法稳定

## 基本思想
- 将序列分为左右两组
- 重复第一步，直至左右两组里面的元素数量为1
- 从小到大合并左右两组
- 完成合并

## 算法
```bash
def merge_sort(lst):  
    if len(lst) <= 1:  
        return lst  
    mid = len(lst) // 2  
    print 'left: ', lst[: mid]  
    print 'right: ', lst[mid:]  
    print ''  
    left = merge_sort(lst[: mid])  
    right = merge_sort(lst[mid:])  
    return merge(left, right)  


def merge(left, right):  
    print 'left: ', left  
    print 'right: ', right  
    res = []  
    i, j = 0, 0  
    while i < len(left) and j < len(right):  
        if left[i] <= right[j]:  
            res.append(left[i])  
            i += 1  
        else:  
            res.append(right[j])  
            j += 1  
    res += left[i:]  
    res += right[j:]  
    print 'res: ', res  
    print '***'  
    return res  
```
## 测试
```bash
lst=[7,8,4,1,76,45,2,12,14,15]
merge_sort(lst)
```
### 步骤过程
```bash
left:  [7, 8, 4, 1, 76]
right:  [45, 2, 12, 14, 15]

left:  [7, 8]
right:  [4, 1, 76]

left:  [7]
right:  [8]

left:  [7]
right:  [8]
res:  [7, 8]
***
left:  [4]
right:  [1, 76]

left:  [1]
right:  [76]

left:  [1]
right:  [76]
res:  [1, 76]
***
left:  [4]
right:  [1, 76]
res:  [1, 4, 76]
***
left:  [7, 8]
right:  [1, 4, 76]
res:  [1, 4, 7, 8, 76]
***
left:  [45, 2]
right:  [12, 14, 15]

left:  [45]
right:  [2]

left:  [45]
right:  [2]
res:  [2, 45]
***
left:  [12]
right:  [14, 15]

left:  [14]
right:  [15]

left:  [14]
right:  [15]
res:  [14, 15]
***
left:  [12]
right:  [14, 15]
res:  [12, 14, 15]
***
left:  [2, 45]
right:  [12, 14, 15]
res:  [2, 12, 14, 15, 45]
***
left:  [1, 4, 7, 8, 76]
right:  [2, 12, 14, 15, 45]
res:  [1, 2, 4, 7, 8, 12, 14, 15, 45, 76]
***
```
### 最终结果
```bash
[1, 2, 4, 7, 8, 12, 14, 15, 45, 76]
```