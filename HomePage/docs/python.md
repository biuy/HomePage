# python基础语法


## 数据类型

	#!/usr/bin/env python3
	# -*- coding: utf-8 -*-


ord()函数获取字符的整数表示
chr()函数把编码转换为对应的字符

用r''表示''内部的字符串默认不转义

	name = input()
	
name为字符串类型

	>>> print(r'\\\t\\')
	\\\t\\

	>>> print('''line1                                      
	... line2                                               
	... line3''')                                           
	line1                                                   
	line2                                                   
	line3
	
	
一个布尔值只有True、False两种值
布尔值可以用and、or和not运算。
None是一个特殊的空值。

还有一种除法是`//`，称为地板除，两个整数的除法仍然是整数

字符串类型是str

对bytes类型的数据用带b前缀的单引号或双引号表示,在bytes中，无法显示为ASCII字符的字节，用\x##显示。

encode()方法可以编码为指定的bytes;把bytes变为str，就需要用decode()方法

`len()函数`：
	
	len('ABC')


	print('%2d-%02d' % (3, 1))
	3-01
	print('%.2f' % 3.1415926)

如果你不太确定应该用什么，%s永远起作用，它会把任何数据类型转换为字符串：

`format()`方法

	'Hello, {0}, 成绩提升了 {1:.1f}%'.format('小明', 17.125)

## list

	classmates = ['Michael', 'Bob', 'Tracy']

`len()`函数可以获得list元素的个数

	len(classmates)
	
要取最后一个元素，除了计算索引位置外，还可以用`-1`做索引直接获取最后一个元素：

	classmates[-1]
	
可以往list中追加元素到末尾：
	
	classmates.append('Adam')

把元素`插入`到指定的位置

	classmates.insert(1, 'Jack')

删除list末尾的元素，用`pop()`方法：

	classmates.pop()

`pop(i)`方法

	classmates.pop(1)

替换

	classmates[1] = 'Sarah'

数据类型也可以不同

一个list中一个元素也没有，就是一个空的list

## tuple

tuple一旦初始化就不能修改

没有append()，insert()

定义一个tuple
	
	t = (1, 2)

只有1个元素的tuple定义时必须加一个逗号,，来消除歧义：

	 t = (1,)

tuple内可以放list,可变

## 条件和循环

	if <条件判断1>:
	    <执行1>
	elif <条件判断2>:
	    <执行2>
	elif <条件判断3>:
	    <执行3>
	else:
	    <执行4>
	
for...in循环，依次把list或tuple中的每个元素迭代出来
`range(5)`生成的序列是从0开始小于5的整数

	>>> list(range(5))
	[0, 1, 2, 3, 4]
	
	for x in range(101):
	    sum = sum + x
	  
while  
	  
	while n <= 100:
	    if n > 10: 
	        break 
	        #continue
	    print(n)
	    n = n + 1
	
## 字典dict

	>>> d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
	>>> d['Michael']
	95
	
放入

	d['Adam'] = 67

避免key不存在的错误，有两种办法，一是通过in判断key是否存在：

	>>> 'Thomas' in d
	False
	
二是通过dict提供的get()方法，如果key不存在，可以返回None，或者自己指定的value：
	
	>>> d.get('Thomas', -1)
	-1
	
要删除一个key，用pop(key)方法，对应的value也会从dict中删除：
	
	d.pop('Bob')
	
和list比较，dict有以下几个特点：

	1.	查找和插入的速度极快，不会随着key的增加而变慢；
	2.	需要占用大量的内存，内存浪费多。

而list相反：

	1.	查找和插入的时间随着元素的增加而增加；
	2.	占用空间小，浪费内存很少。
	
所以，dict是用空间来换取时间的一种方法

## set

在set中，没有重复的key。
无序

要创建一个set，需要提供一个list作为输入集合：

	s = set([1, 2, 3])

传入的参数[1, 2, 3]是一个list，而显示的{1, 2, 3}只是告诉你这个set内部有1，2，3这3个元素，显示的顺序也不表示set是有序的。。
		
	s.add(4)

	s.remove(4)

两个set可以做数学意义上的交集、并集等操作：

	s1 & s2
	s1 | s2

## 函数
定义函数

以自定义一个求绝对值的my_abs函数为例：
	
	def my_abs(x):
	    if x >= 0:
	        return x
	    else:
	        return -x
        
如果想定义一个什么事也不做的空函数，可以用pass语句：

	def nop():
		pass
 	   
实际上pass可以用来作为占位符，比如现在还没想好怎么写函数的代码，就可以先放一个pass，让代码能运行起来。

	if age >= 18:
	    pass
	    
修改一下my_abs的定义，对参数类型做检查，只允许整数和浮点数类型的参数

	def my_abs(x):
	    if not isinstance(x, (int, float)):
	        raise TypeError('bad operand type')
	    if x >= 0:
	        return x
	    else:
	        return -x
	        
返回多个值(tuple)

	return x,y

### 默认参数

> 必选参数在前，默认参数在后，否则Python的解释器会报错

当函数有多个参数时，把变化大的参数放前面，变化小的参数放后面。变化小的参数就可以作为默认参数。
	
当不按顺序提供部分默认参数时，需要把参数名写上。

> 定义默认参数要牢记一点：默认参数必须指向不变对象！（因为不是可变的形参了）

### 可变参数


	

	        
	        


	

