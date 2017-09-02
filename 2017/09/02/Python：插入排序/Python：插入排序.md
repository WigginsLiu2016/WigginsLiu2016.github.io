---
title: Python：插入排序
date: 2017-09-02 15:50:40
tags: [python]
description: 插入排序：空间复杂度为O（1），时间复杂度为[O（n），O（n^2）]，算法稳定，具有适应性
categories: Python
keywords: Python

---

### 插入排序算法
> 空间复杂度为O（1），时间复杂度为[O（n），O（n^2）]，算法稳定，具有适应性

#### 基本思想
- 当前需要排序的元素跟已经排好序的最后一个元素进行比较，如果满足条件则进行下面的操作，否则循环到下一个
要排序的元素
- 缓存当前需要排序的元素，以便找到正确的位置进行插入
- 排序的元素跟排好序的元素进行比较，大的向后移（升序）
- 当前要排序的元素，插入到正确的位置

#### 算法

```bash
def Insert_sort(lst):  
    for i in range(1, len(lst)):  
        temp = lst[i]  
        j = i  
        while j > 0 and temp < lst[j - 1]:  
            lst[j] = lst[j - 1]  
            j -= 1  
        lst[j] = temp  
        print 'lst: ', lst  
    return lst  
```