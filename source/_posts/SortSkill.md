---
title: SortSkill
date: 2019-02-21 15:55:25
tags:
---

## 排序大小写字母数字
    s = "SortIng1234"
    f1 = "".join(sorted(s, key=lambda x: (x.isdigit(), x.isdigit() and int(x) % 2 == 0, x, x.isupper(), x.islower()),reverse=True))
    print(f)
    s = "SortIng1234"
    m = "".join(sorted(s, key=lambda x: (x, x.isdigit(), x.isdigit() and int(x) % 2 == 0, x.isupper(), x.islower())))
    print(m)
    s = "SortIng1234"
    f2 = "".join(sorted(s, key=lambda x: (x.isdigit(), x.isdigit() and int(x) % 2 == 0, x.isupper(), x.islower(), x)))
    print(f)

    a = '1232312312340'
    f3 = "".join(sorted(a, key=lambda x: (x.isdigit() and int(x) % 2 == 0, x.isdigit(),)))
    print(f)
    a = '1232312312340'
    f4 = "".join(sorted(a, key=lambda x: (x.isdigit() and int(x) % 2 == 0, x.isdigit(), x)))
    print(f)