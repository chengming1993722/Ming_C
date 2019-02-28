---
title: reverseListNode
date: 2019-02-28 11:24:54
categories:
- ListNode
tags:
- sort
---


## ReverseListNode
    class ListNode:
    def __init__(self, x):
        self.val = x
        self.next = None


    def nodereverse(head):
        if head is None and head.next is None:
            return head
        pre = None
        while head:
            '''先用tmp保存head的下一个节点信息'''
            tmp = head.next
            '''让head指向pre'''
            head.next = pre
            pre = head
            head = tmp
        return pre


    head = ListNode(1);  # 测试代码
    p1 = ListNode(2);  # 建立链表1->2->3->4->None;
    p2 = ListNode(3);
    p3 = ListNode(4);
    head.next = p1;
    p1.next = p2;
    p2.next = p3;
    p = nodereverse(head);  # 输出链表 4->3->2->1->None
    print(p)
    while p:
        print(p.val)
        p = p.next
