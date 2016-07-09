---
layout: post
title: Python:filter, map, reduce, lambda
description: 基础语法，以前很少用，看了一遍，还是记录下来比较好
category: coding
---

## Python的filter, map, reduce, lambda学习


虽然写过几个简单的python的应用，但是很多语法基本都没用到过，每次在网上看完之后就忘记了，既然开了Blog，学过的就顺手记录下来吧，省得以后用到再去查。
btw: 我一直用的是python2.7， 据说下面的函数在python3中被移到了functools，请自行验证

***

## lambda

lambda是匿名函数, [知乎](https://www.zhihu.com/question/20125256)的这篇文章里有详细的解释，lambda x:x+1 指的就是一个入参是x，返回值是x+1的函数，一般不会定义太过复杂的lambda函数，且lambda一般会与下面提到的filter/map/reduce组合使用：

    a = lambda x:x*2
    a(3)   # 结果是6

***

## filter

filter(function, sequence), 顾名思义，这是一个用来筛选的函数，入参有两个，第一个是筛选函数，第二个是一个sequence，filter会对sequence中的每个元素调用筛选函数，最后会将执行结果为True的item组成一个List/String/Tuple返回，将filter与lambda组合后可以极大的简化代码(同时需要注意的是可能会导致代码可读性下降)。
下面的代码通过lambda定义了一个匿名函数，该函数会检查入参是否是偶数，如果是偶数返回True，filter则通过该lambda函数对11-14之间的数字进行了筛选，结果返回11-19之间的偶数的list：

    filter(lambda x:x%2==0, range(11, 15)) # [12, 14]

***

## map

map(function, sequence), 理解了filter和lambda之后，map其实很类似，map的作用是对sequence中的item依次执行function，将结果组成一个list返回，直接将上面的filter改成map，其他所有内容保持一致，会得到一个由True和False组成的list：

    map(lambda x:x%2==0, range(11, 15)) # [False, True, False, True]

***

## reduce

reduce(function, sequence, starting_value), reduce对sequence中的item顺序迭代调用function，用function先对集合中的第一二个数据进行操作，得到的结果再与第三个数据用function进行运算，最后得到一个结果，如果有starting_value，还可以作为初始值来调用：

    reduce(lambda x,y:x+y, [1,2,3]) # 6
    reduce(lambda x,y:x+y, [], 20)  #20

***
