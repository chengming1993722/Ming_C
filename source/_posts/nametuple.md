---
title: nametuple
date: 2018-07-31 14:32:25
tags:
---

### python3 nametuple使用
#### namedtuple是继承自tuple的子类。namedtuple创建一个和tuple类似的对象，而且对象拥有可访问的属性  
collections.namedtuple(typename, field_names, *, rename=False, defaults=None, module=None)  

返回名为typename的新元组子类。新子类用于创建类似元组的对象，这些对象具有可通过属性查找访问的字段以及可索引  
和可​​迭代的字段。子类的实例还有一个有用的docstring（带有typename和field_names）和一个有用的__repr __（）方法，  
它以name = value格式列出元组内容

    from collections import namedtuple
    #定义一个商品类型goods, 商品拥有name,number,price属性
    Goods = namedtuple('Goods',['name','number','price'])
    #创建一个Goods对象
    goods = Goods(name='apple',number=3,price=2.5)
    #也可以使用_make方法来创建一个Goods对象
    goods = Goods._make(['apple',3,2.5])
    print(goods.number*goods.price)
    # result : 1
    name,number,price=goods
    print(f"{name}'s price is {price}$ per kilogram,which has {number}kg,so tottal price is {number*price}$")

#### _make(iterable)方法：用一个已存在的序列或可迭代的对象生成实例
    orange = ['orange','2','4']
    goods = Goods._make(orange)
    print(goods)
    # result : Goods(name='orange', number='2', price='4')
    orange=('orange','2','4')
    goods = Goods._make(orange)
    print(goods)
    # result : Goods(name='orange', number='2', price='4')

#### _asdict() : 返回一个OrderedDict
    org = goods._asdict()
    #result : OrderedDict([('name', 'orange'), ('number', '2'), ('price', '4')])

#### _replace(*kwargs) : 替换指定属性的值
    goods._replace(name='juice')
    print(goods._replace(name='juice'))
    $ result : Goods(name='juice', number='2', price='4')

#### _fields ： 返回一个包含Goods对象属性（'name','number','price'）的元组
    print(goods._fileds)
    #return : （'name','number','price'）

#### _fields_defaults: 设置默认值
    ***注：此方法为python3.7 新加的方法**
    >>> Account = namedtuple('Account', ['type', 'balance'], defaults=[0])
    >>> Account._fields_defaults
    {'balance': 0}
    >>> Account('premium')
    Account(type='premium', balance=0)

#### 一些用法
    >>>getattr(goods, 'name')
    orange
    >>>apple = {'name':'apple','number':3,'price':5}
    >>>goods = Goods(**apple)
    Goods(name='apple', number=3, price=5)

    '''' 星号*把序列/集合解包（unpack）成位置参数，两个星号**把字典解包成关键字参数 '''


