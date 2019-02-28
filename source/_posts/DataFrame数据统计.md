---
title: DataFrame数据统计
date: 2018-08-22 19:18:16
categories:
- DataFrame
tags:
- groupby,列操作
---

## DataFrame 统计数据条目

### DataFrame.groupby('列名').count()
    rtn.groupby('s_hw_everyday_level').count() 
    # 统计各级‘s_hw_everyday_level’的个数

### DataFrame['列名'].shape
    rtn['s_hw_everyday_level].shape 
    #返回DateFrame的列数

### DataFrame['列名']
    rtn['s_hw_everyday_level].count
    #返回's_hw_everyday_level'的数量

