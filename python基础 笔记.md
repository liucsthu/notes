# python基础 笔记

## 数据类型转换

| 函数                    | 描述                              |
| --------------------- | ------------------------------- |
| int(x [,base])        | 将x转换为一个整数                       |
| long(x [,base] )      | 将x转换为一个长整数                      |
| float(x)              | 将x转换到一个浮点数                      |
| complex(real [,imag]) | 创建一个复数                          |
| str(x)                | 将对象 x 转换为字符串                    |
| repr(x)               | 将对象 x 转换为表达式字符串                 |
| eval(str)             | 用来计算在字符串中的有效Python表达式,并返回一个对象   |
| tuple(s)              | 将序列 s 转换为一个元组                   |
| list(s)               | 将序列 s 转换为一个列表                   |
| set(s)                | 转换为可变集合                         |
| dict(d)               | 创建一个字典。d 必须是一个序列 (key,value)元组。 |
| frozenset(s)          | 转换为不可变集合                        |
| chr(x)                | 将一个整数转换为一个字符                    |
| unichr(x)             | 将一个整数转换为Unicode字符               |
| ord(x)                | 将一个字符转换为它的整数值                   |
| hex(x)                | 将一个整数转换为一个十六进制字符串               |
| oct(x) bin(x)         | 将一个整数转换为一个八进制字符串                |

## python 运算符

| 运算符  | 描述                        | 实例                                       |
| ---- | ------------------------- | ---------------------------------------- |
| +    | 加 - 两个对象相加                | a + b 输出结果 30                            |
| -    | 减 - 得到负数或是一个数减去另一个数       | a - b 输出结果 -10                           |
| *    | 乘 - 两个数相乘或是返回一个被重复若干次的字符串 | a * b 输出结果 200                           |
| /    | 除 - x除以y                  | b / a 输出结果 2                             |
| %    | 取模 - 返回除法的余数              | b % a 输出结果 0                             |
| **   | 幂 - 返回x的y次幂               | a**b 为10的20次方， 输出结果 100000000000000000000 |
| //   | 取整除 - 返回商的整数部分            | 9//2 输出结果 4 , 9.0//2.0 输出结果 4.0          |

## Python身份运算符

身份运算符用于比较两个对象的存储单元

| 运算符    | 描述                       | 实例                                       |
| ------ | ------------------------ | ---------------------------------------- |
| is     | is是判断两个标识符是不是引用自一个对象     | x is y, 如果 id(x) 等于 id(y) , **is** 返回结果 1 |
| is not | is not是判断两个标识符是不是引用自不同对象 | x is not y, 如果 id(x) 不等于 id(y). **is not** 返回结果 1 |

## Python数学函数

| 函数                                       | 返回值 ( 描述 )                               |
| ---------------------------------------- | ---------------------------------------- |
| [abs(x)](http://www.runoob.com/python/func-number-abs.html) | 返回数字的绝对值，如abs(-10) 返回 10                 |
| [ceil(x)](http://www.runoob.com/python/func-number-ceil.html) | 返回数字的上入整数，如math.ceil(4.1) 返回 5           |
| [cmp(x, y)](http://www.runoob.com/python/func-number-cmp.html) | 如果 x < y 返回 -1, 如果 x == y 返回 0, 如果 x > y 返回 1 |
| [exp(x)](http://www.runoob.com/python/func-number-exp.html) | 返回e的x次幂(ex),如math.exp(1) 返回2.718281828459045 |
| [fabs(x)](http://www.runoob.com/python/func-number-fabs.html) | 返回数字的绝对值，如math.fabs(-10) 返回10.0          |
| [floor(x)](http://www.runoob.com/python/func-number-floor.html) | 返回数字的下舍整数，如math.floor(4.9)返回 4           |
| [log(x)](http://www.runoob.com/python/func-number-log.html) | 如math.log(math.e)返回1.0,math.log(100,10)返回2.0 |
| [log10(x)](http://www.runoob.com/python/func-number-log10.html) | 返回以10为基数的x的对数，如math.log10(100)返回 2.0     |
| [max(x1, x2,...)](http://www.runoob.com/python/func-number-max.html) | 返回给定参数的最大值，参数可以为序列。                      |
| [min(x1, x2,...)](http://www.runoob.com/python/func-number-min.html) | 返回给定参数的最小值，参数可以为序列。                      |
| [modf(x)](http://www.runoob.com/python/func-number-modf.html) | 返回x的整数部分与小数部分，两部分的数值符号与x相同，整数部分以浮点型表示。   |
| [pow(x, y)](http://www.runoob.com/python/func-number-pow.html) | x**y 运算后的值。                              |
| [round(x [,n\])](http://www.runoob.com/python/func-number-round.html) | 返回浮点数x的四舍五入值，如给出n值，则代表舍入到小数点后的位数。        |
| [sqrt(x)](http://www.runoob.com/python/func-number-sqrt.html) | 返回数字x的平方根，数字可以为负数，返回类型为实数，如math.sqrt(4)返回 2+0j |

## Python随机数函数

随机数可以用于数学，游戏，安全等领域中，还经常被嵌入到算法中，用以提高算法效率，并提高程序的安全性。

Python包含以下常用随机数函数：

| 函数                                       | 描述                                       |
| ---------------------------------------- | ---------------------------------------- |
| [choice(seq)](http://www.runoob.com/python/func-number-choice.html) | 从序列的元素中随机挑选一个元素，比如random.choice(range(10))，从0到9中随机挑选一个整数。 |
| [randrange ([start,\] stop [,step])](http://www.runoob.com/python/func-number-randrange.html) | 从指定范围内，按指定基数递增的集合中获取一个随机数，基数缺省值为1        |
| [random()](http://www.runoob.com/python/func-number-random.html) | 随机生成下一个实数，它在[0,1)范围内。                    |
| [seed([x\])](http://www.runoob.com/python/func-number-seed.html) | 改变随机数生成器的种子seed。如果你不了解其原理，你不必特别去设定seed，Python会帮你选择seed。 |
| [shuffle(lst)](http://www.runoob.com/python/func-number-shuffle.html) | 将序列的所有元素随机排序                             |
| [uniform(x, y)](http://www.runoob.com/python/func-number-uniform.html) | 随机生成下一个实数，它在[x,y]范围内。                    |

------

## Python三角函数

Python包括以下三角函数：

| 函数                                       | 描述                                    |
| ---------------------------------------- | ------------------------------------- |
| [acos(x)](http://www.runoob.com/python/func-number-acos.html) | 返回x的反余弦弧度值。                           |
| [asin(x)](http://www.runoob.com/python/func-number-asin.html) | 返回x的反正弦弧度值。                           |
| [atan(x)](http://www.runoob.com/python/func-number-atan.html) | 返回x的反正切弧度值。                           |
| [atan2(y, x)](http://www.runoob.com/python/func-number-atan2.html) | 返回给定的 X 及 Y 坐标值的反正切值。                 |
| [cos(x)](http://www.runoob.com/python/func-number-cos.html) | 返回x的弧度的余弦值。                           |
| [hypot(x, y)](http://www.runoob.com/python/func-number-hypot.html) | 返回欧几里德范数 sqrt(x*x + y*y)。             |
| [sin(x)](http://www.runoob.com/python/func-number-sin.html) | 返回的x弧度的正弦值。                           |
| [tan(x)](http://www.runoob.com/python/func-number-tan.html) | 返回x弧度的正切值。                            |
| [degrees(x)](http://www.runoob.com/python/func-number-degrees.html) | 将弧度转换为角度,如degrees(math.pi/2) ， 返回90.0 |
| [radians(x)](http://www.runoob.com/python/func-number-radians.html) | 将角度转换为弧度                              |

## Python数学常量

| 常量   | 描述                   |
| ---- | -------------------- |
| pi   | 数学常量 pi（圆周率，一般以π来表示） |
| e    | 数学常量 e，e即自然常数（自然常数）。 |

## Python转义字符

在需要在字符中使用特殊字符时，python用反斜杠(\)转义字符。如下表：

| 转义字符    | 描述                        |
| ------- | ------------------------- |
| \(在行尾时) | 续行符                       |
| \\      | 反斜杠符号                     |
| \'      | 单引号                       |
| \"      | 双引号                       |
| \a      | 响铃                        |
| \b      | 退格(Backspace)             |
| \e      | 转义                        |
| \000    | 空                         |
| \n      | 换行                        |
| \v      | 纵向制表符                     |
| \t      | 横向制表符                     |
| \r      | 回车                        |
| \f      | 换页                        |
| \oyy    | 八进制数，yy代表的字符，例如：\o12代表换行  |
| \xyy    | 十六进制数，yy代表的字符，例如：\x0a代表换行 |
| \other  | 其它的字符以普通格式输出              |

## python字符串格式化符号:

| 符   号 | 描述                 |
| ----- | ------------------ |
| %c    | 格式化字符及其ASCII码      |
| %s    | 格式化字符串             |
| %d    | 格式化整数              |
| %u    | 格式化无符号整型           |
| %o    | 格式化无符号八进制数         |
| %x    | 格式化无符号十六进制数        |
| %X    | 格式化无符号十六进制数（大写）    |
| %f    | 格式化浮点数字，可指定小数点后的精度 |
| %e    | 用科学计数法格式化浮点数       |
| %E    | 作用同%e，用科学计数法格式化浮点数 |
| %g    | %f和%e的简写           |
| %G    | %f 和 %E 的简写        |
| %p    | 用十六进制数格式化变量的地址     |

格式化操作符辅助指令:

| 符号    | 功能                                       |
| ----- | ---------------------------------------- |
| *     | 定义宽度或者小数点精度                              |
| -     | 用做左对齐                                    |
| +     | 在正数前面显示加号( + )                           |
| <sp>  | 在正数前面显示空格                                |
| #     | 在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X') |
| 0     | 显示的数字前面填充'0'而不是默认的空格                     |
| %     | '%%'输出一个单一的'%'                           |
| (var) | 映射变量(字典参数)                               |
| m.n.  | m 是显示的最小总宽度,n 是小数点后的位数(如果可用的话)           |

Python 中定义一个 Unicode 字符串和定义一个普通字符串一样简单：

```python
>>> u'Hello World !'
u'Hello World !'
```

## **字典的基本操作**

1. 如何访问字典中的值？

   adict[key] 形式返回键key对应的值value，如果key不在字典中会引发一个KeyError。

2. 如何检查key是否在字典中？

   a、has_key()方法 形如：adict.haskey(‘name') 有–>True，无–>False
   b、in 、not in   形如：'name' in adict      有–>True，无–>False

3. 如何更新字典？

   a、添加一个数据项（新元素）或键值对
   adict[new_key] = value 形式添加一个项
   b、更新一个数据项（元素）或键值对
   adict[old_key] = new_value
   c、删除一个数据项（元素）或键值对
   del adict[key] 删除键key的项 / del adict 删除整个字典
   adict.pop(key) 删除键key的项并返回key对应的 value值

4. len() 返回字典的长度

5. hash() 返回对象的哈希值，可以用来判断一个对象能否用来作为字典的键

6. dict() 工厂函数，用来创建字典

**字典的方法**

| 函数                                       | 解释                                       |
| ---------------------------------------- | ---------------------------------------- |
| adict.keys()                             | 返回一个包含字典所有KEY的列表；                        |
| adict.values()                           | 返回一个包含字典所有value的列表                       |
| adict.items()                            | 返回一个包含所有（键，值）元祖的列表；                      |
| adict.clear()                            | 删除字典中的所有项或元素                             |
| adict.copy()                             | 返回一个字典浅拷贝的副本                             |
| adict.fromkeys(seq, val=None)            | 创建并返回一个新字典，以seq中的元素做该字典的键，val做该字典中所		有键对应的初始值（默认为None）； |
| adict.get(key, default = None)           | 返回字典中key对应的值，若key不存在字典中，则返回default的值	（default默认为None）； |
| adict.has_key(key)                       | 如果key在字典中，返回True，否则返回False。 现在用 in 、 not in； |
| adict.iteritems()、adict.iterkeys()、adict.itervalues() | 与它们对应的非迭代方法一样，不同的是它们返回一个迭代子，而不是一个列表；     |
| adict.pop(key[,default])                 | 和get方法相似。如果字典中存在key，删除并返回key对应的vuale；如果key不存在，且没有给出default的值，则引发keyerror异常； |
| adict.setdefault(key, default=None)      | 和set()方法相似，但如果字典中不存在Key键，由 adict[key] = default 为它赋值； |
| adict.update(bdict)                      | 将字典bdict的键值对添加到字典adict中。                 |

## python 时间处理

Python 程序能用很多方式处理日期和时间，转换日期格式是一个常见的功能。

Python 提供了一个 time 和 calendar 模块可以用于格式化日期和时间。

时间间隔是以秒为单位的浮点小数。

每个时间戳都以自从1970年1月1日午夜（历元）经过了多长时间来表示。

Python 的 time 模块下有很多函数可以转换常见日期格式。如函数time.time()用于获取当前时间戳, 如下实例：

```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import time;  # 引入time模块

ticks = time.time()
print "当前时间戳为:", ticks
```



输出结果

```
当前时间戳为: 1459994552.51
```

**==时间戳单位最适于做日期运算。但是1970年之前的日期就无法以此表示了。太遥远的日期也不行，UNIX和Windows只支持到2038年。==**

| 序号   | 字段     | 值                        |
| ---- | ------ | ------------------------ |
| 0    | 4位数年   | 2008                     |
| 1    | 月      | 1 到 12                   |
| 2    | 日      | 1到31                     |
| 3    | 小时     | 0到23                     |
| 4    | 分钟     | 0到59                     |
| 5    | 秒      | 0到61 (60或61 是闰秒)         |
| 6    | 一周的第几日 | 0到6 (0是周一)               |
| 7    | 一年的第几日 | 1到366 (儒略历)              |
| 8    | 夏令时    | -1, 0, 1, -1是决定是否为夏令时的旗帜 |

上述也就是struct_time元组。这种结构具有如下属性：

| 序号   | 属性       | 值                        |
| ---- | -------- | ------------------------ |
| 0    | tm_year  | 2008                     |
| 1    | tm_mon   | 1 到 12                   |
| 2    | tm_mday  | 1 到 31                   |
| 3    | tm_hour  | 0 到 23                   |
| 4    | tm_min   | 0 到 59                   |
| 5    | tm_sec   | 0 到 61 (60或61 是闰秒)       |
| 6    | tm_wday  | 0到6 (0是周一)               |
| 7    | tm_yday  | 1 到 366(儒略历)             |
| 8    | tm_isdst | -1, 0, 1, -1是决定是否为夏令时的旗帜 |

## 获取当前时间

从返回浮点数的时间辍方式向时间元组转换，只要将浮点数传递给如localtime之类的函数。

```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import time

localtime = time.localtime(time.time())
print "本地时间为 :", localtime
```

以上实例输出结果：

```
本地时间为 : time.struct_time(tm_year=2016, tm_mon=4, tm_mday=7, tm_hour=10, tm_min=3, tm_sec=27, tm_wday=3, tm_yday=98, tm_isdst=0)
```

### 获取格式化的时间

你可以根据需求选取各种格式，但是最简单的获取可读的时间模式的函数是asctime():

```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import time

localtime = time.asctime( time.localtime(time.time()) )
print "本地时间为 :", localtime
```

以上实例输出结果：

```
本地时间为 : Thu Apr  7 10:05:21 2016
```

### 格式化日期

```python
time.strftime(format[, t])
```

python中时间日期格式化符号：

* %y 两位数的年份表示（00-99）
* %Y 四位数的年份表示（000-9999）
* %m 月份（01-12）
* %d 月内中的一天（0-31）
* %H 24小时制小时数（0-23）
* %I 12小时制小时数（01-12）
* %M 分钟数（00=59）
* %S 秒（00-59）
* %a 本地简化星期名称
* %A 本地完整星期名称
* %b 本地简化的月份名称
* %B 本地完整的月份名称
* %c 本地相应的日期表示和时间表示
* %j 年内的一天（001-366）
* %p 本地A.M.或P.M.的等价符
* %U 一年中的星期数（00-53）星期天为星期的开始
* %w 星期（0-6），星期天为星期的开始
* %W 一年中的星期数（00-53）星期一为星期的开始
* %x 本地相应的日期表示
* %X 本地相应的时间表示
* %Z 当前时区的名称
* %% %号本身

### 获取某月日历

Calendar模块有很广泛的方法用来处理年历和月历，例如打印某月的月历：

```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import calendar

cal = calendar.month(2016, 1)
print "以下输出2016年1月份的日历:"
print cal;
```

以上实例输出结果：

```python
以下输出2016年1月份的日历:
    January 2016
Mo Tu We Th Fr Sa Su
             1  2  3
 4  5  6  7  8  9 10
11 12 13 14 15 16 17
18 19 20 21 22 23 24
25 26 27 28 29 30 31
```

### Time 模块

| 序号   | 函数及描述                                    |
| ---- | ---------------------------------------- |
| 1    | [time.altzone](http://www.runoob.com/python/att-time-altzone.html)返回格林威治西部的夏令时地区的偏移秒数。如果该地区在格林威治东部会返回负值（如西欧，包括英国）。对夏令时启用地区才能使用。 |
| 2    | [time.asctime([tupletime\])](http://www.runoob.com/python/att-time-asctime.html)接受时间元组并返回一个可读的形式为"Tue Dec 11 18:07:14 2008"（2008年12月11日 周二18时07分14秒）的24个字符的字符串。 |
| 3    | [time.clock( )](http://www.runoob.com/python/att-time-clock.html)用以浮点数计算的秒数返回当前的CPU时间。用来衡量不同程序的耗时，比time.time()更有用。 |
| 4    | [time.ctime([secs\])](http://www.runoob.com/python/att-time-ctime.html)作用相当于asctime(localtime(secs))，未给参数相当于asctime() |
| 5    | [time.gmtime([secs\])](http://www.runoob.com/python/att-time-gmtime.html)接收时间辍（1970纪元后经过的浮点秒数）并返回格林威治天文时间下的时间元组t。注：t.tm_isdst始终为0 |
| 6    | [time.localtime([secs\])](http://www.runoob.com/python/att-time-localtime.html)接收时间辍（1970纪元后经过的浮点秒数）并返回当地时间下的时间元组t（t.tm_isdst可取0或1，取决于当地当时是不是夏令时）。 |
| 7    | [time.mktime(tupletime)](http://www.runoob.com/python/att-time-mktime.html)接受时间元组并返回时间辍（1970纪元后经过的浮点秒数）。 |
| 8    | [time.sleep(secs)](http://www.runoob.com/python/att-time-sleep.html)推迟调用线程的运行，secs指秒数。 |
| 9    | [time.strftime(fmt[,tupletime\])](http://www.runoob.com/python/att-time-strftime.html)接收以时间元组，并返回以可读字符串表示的当地时间，格式由fmt决定。 |
| 10   | [time.strptime(str,fmt='%a %b %d %H:%M:%S %Y')](http://www.runoob.com/python/att-time-strptime.html)根据fmt的格式把一个时间字符串解析为时间元组。 |
| 11   | [time.time( )](http://www.runoob.com/python/att-time-time.html)返回当前时间的时间戳（1970纪元后经过的浮点秒数）。 |
| 12   | [time.tzset()](http://www.runoob.com/python/att-time-tzset.html)根据环境变量TZ重新初始化时间相关设置。 |

Time模块包含了以下2个非常重要的属性：

| 序号   | 属性及描述                                    |
| ---- | ---------------------------------------- |
| 1    | **time.timezone**属性time.timezone是当地时区（未启动夏令时）距离格林威治的偏移秒数（>0，美洲;<=0大部分欧洲，亚洲，非洲）。 |
| 2    | **time.tzname**属性time.tzname包含一对根据情况的不同而不同的字符串，分别是带夏令时的本地时区名称，和不带的。 |

### 日历（Calendar）模块

此模块的函数都是日历相关的，例如打印某月的字符月历。

星期一是默认的每周第一天，星期天是默认的最后一天。更改设置需调用calendar.setfirstweekday()函数。模块包含了以下内置函数：

| 序号   | 函数及描述                                    |
| ---- | ---------------------------------------- |
| 1    | **calendar.calendar(year,w=2,l=1,c=6)**返回一个多行字符串格式的year年年历，3个月一行，间隔距离为c。 每日宽度间隔为w字符。每行长度为21* W+18+2* C。l是每星期行数。 |
| 2    | **calendar.firstweekday( )**返回当前每周起始日期的设置。默认情况下，首次载入caendar模块时返回0，即星期一。 |
| 3    | **calendar.isleap(year)**是闰年返回True，否则为false。 |
| 4    | **calendar.leapdays(y1,y2)**返回在Y1，Y2两年之间的闰年总数。 |
| 5    | **calendar.month(year,month,w=2,l=1)**返回一个多行字符串格式的year年month月日历，两行标题，一周一行。每日宽度间隔为w字符。每行的长度为7* w+6。l是每星期的行数。 |
| 6    | **calendar.monthcalendar(year,month)**返回一个整数的单层嵌套列表。每个子列表装载代表一个星期的整数。Year年month月外的日期都设为0;范围内的日子都由该月第几日表示，从1开始。 |
| 7    | **calendar.monthrange(year,month)**返回两个整数。第一个是该月的星期几的日期码，第二个是该月的日期码。日从0（星期一）到6（星期日）;月从1到12。 |
| 8    | **calendar.prcal(year,w=2,l=1,c=6)**相当于 print calendar.calendar(year,w,l,c). |
| 9    | **calendar.prmonth(year,month,w=2,l=1)**相当于 print calendar.calendar（year，w，l，c）。 |
| 10   | **calendar.setfirstweekday(weekday)**设置每周的起始日期码。0（星期一）到6（星期日）。 |
| 11   | **calendar.timegm(tupletime)**和time.gmtime相反：接受一个时间元组形式，返回该时刻的时间辍（1970纪元后经过的浮点秒数）。 |
| 12   | **calendar.weekday(year,month,day)**返回给定日期的日期码。0（星期一）到6（星期日）。月份为 1（一月） 到 12（12月）。 |

### 其他相关模块和函数

在Python中，其他处理日期和时间的模块还有：

* [datetime模块](http://docs.python.org/library/datetime.html#module-datetime)
* [pytz模块](http://www.twinsun.com/tz/tz-link.htm)
* [dateutil模块](http://labix.org/python-dateutil)

## 函数

**dir()函数:**

dir()函数一个排好序的字符串列表，内容是一个模块里定义过的名字。

返回的列表容纳了在一个模块里定义的所有模块，变量和函数。如下一个简单的实例：

```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 导入内置math模块
import math
 
content = dir(math)
 
print content;
```

以上实例输出结果：

```
['__doc__', '__file__', '__name__', 'acos', 'asin', 'atan', 
'atan2', 'ceil', 'cos', 'cosh', 'degrees', 'e', 'exp', 
'fabs', 'floor', 'fmod', 'frexp', 'hypot', 'ldexp', 'log',
'log10', 'modf', 'pi', 'pow', 'radians', 'sin', 'sinh', 
'sqrt', 'tan', 'tanh']
```

**globals()和locals()函数**

根据调用地方的不同，globals()和locals()函数可被用来返回全局和局部命名空间里的名字。

如果在函数内部调用locals()，返回的是所有能在该函数里访问的命名。

如果在函数内部调用globals()，返回的是所有在该函数里能访问的全局名字。

两个函数的返回类型都是字典。所以名字们能用keys()函数摘取。

------

**reload()函数**

当一个模块被导入到一个脚本，模块顶层部分的代码只会被执行一次。

因此，如果你想重新执行模块里顶层部分的代码，可以用reload()函数。该函数会重新导入之前导入过的模块。语法如下：

```
reload(module_name)
```

在这里，module_name要直接放模块的名字，而不是一个字符串形式。比如想重载hello模块，如下：

```
reload(hello)
```

## Python中的包

包是一个分层次的文件目录结构，它定义了一个由模块及子包，和子包下的子包等组成的Python的应用环境。

考虑一个在Phone目录下的pots.py文件。这个文件有如下源代码：

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
def Pots():
   print "I'm Pots Phone"
   
```

同样地，我们有另外两个保存了不同函数的文件：

* Phone/Isdn.py 含有函数Isdn()
* Phone/G3.py 含有函数G3()

现在，在Phone目录下创建file __init__.py：

* Phone/__init__.py

当你导入Phone时，为了能够使用所有函数，你需要在__init__.py里使用显式的导入语句，如下：

```python
from Pots import Pots
from Isdn import Isdn
from G3 import G3
```

当你把这些代码添加到__init__.py之后，导入Phone包的时候这些类就全都是可用的了。

```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 导入 Phone 包
import Phone
 
Phone.Pots()
Phone.Isdn()
Phone.G3()
```

# Python 文件I/O

本章只讲述所有基本的的I/O函数，更多函数请参考Python标准文档。

## 打印到屏幕

最简单的输出方法是用print语句，你可以给它传递零个或多个用逗号隔开的表达式。此函数把你传递的表达式转换成一个字符串表达式，并将结果写到标准输出如下：

```
#!/usr/bin/python
# -*- coding: UTF-8 -*- 

print "Python 是一个非常棒的语言，不是吗？";
```

你的标准屏幕上会产生以下结果：

```
Python 是一个非常棒的语言，不是吗？
```

## 读取键盘输入

Python提供了两个内置函数从标准输入读入一行文本，默认的标准输入是键盘。如下：

* raw_input
* input

### raw_input函数

raw_input([prompt]) 函数从标准输入读取一个行，并返回一个字符串（去掉结尾的换行符）：

```
#!/usr/bin/python
# -*- coding: UTF-8 -*- 
 
str = raw_input("请输入：");
print "你输入的内容是: ", str
```

这将提示你输入任意字符串，然后在屏幕上显示相同的字符串。当我输入"Hello Python！"，它的输出如下：

```
请输入：Hello Python！
你输入的内容是:  Hello Python！
```

### input函数

**input([prompt])** 函数和 **raw_input([prompt])** 函数基本类似，但是 input 可以接收一个Python表达式作为输入，并将运算结果返回。

```
#!/usr/bin/python
# -*- coding: UTF-8 -*- 
 
str = input("请输入：");
print "你输入的内容是: ", str
```

这会产生如下的对应着输入的结果：

```
请输入：[x*5 for x in range(2,10,2)]
你输入的内容是:  [10, 20, 30, 40]
```

## 打开和关闭文件

现在，您已经可以向标准输入和输出进行读写。现在，来看看怎么读写实际的数据文件。

Python 提供了必要的函数和方法进行默认情况下的文件基本操作。你可以用 **file** 对象做大部分的文件操作。

### open 函数

你必须先用Python内置的open()函数打开一个文件，创建一个file对象，相关的方法才可以调用它进行读写。

语法：

```
file object = open(file_name [, access_mode][, buffering])
```

各个参数的细节如下：

* file_name：file_name变量是一个包含了你要访问的文件名称的字符串值。
* access_mode：access_mode决定了打开文件的模式：只读，写入，追加等。所有可取值见如下的完全列表。这个参数是非强制的，默认文件访问模式为只读(r)。
* buffering:如果buffering的值被设为0，就不会有寄存。如果buffering的值取1，访问文件时会寄存行。如果将buffering的值设为大于1的整数，表明了这就是的寄存区的缓冲大小。如果取负值，寄存区的缓冲大小则为系统默认。

不同模式打开文件的完全列表：

| 模式   | 描述                                       |
| ---- | ---------------------------------------- |
| r    | 以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。         |
| rb   | 以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。   |
| r+   | 打开一个文件用于读写。文件指针将会放在文件的开头。                |
| rb+  | 以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。          |
| w    | 打开一个文件只用于写入。如果该文件已存在则将其覆盖。如果该文件不存在，创建新文件。 |
| wb   | 以二进制格式打开一个文件只用于写入。如果该文件已存在则将其覆盖。如果该文件不存在，创建新文件。 |
| w+   | 打开一个文件用于读写。如果该文件已存在则将其覆盖。如果该文件不存在，创建新文件。 |
| wb+  | 以二进制格式打开一个文件用于读写。如果该文件已存在则将其覆盖。如果该文件不存在，创建新文件。 |
| a    | 打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 |
| ab   | 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 |
| a+   | 打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。 |
| ab+  | 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。 |

## File对象的属性

一个文件被打开后，你有一个file对象，你可以得到有关该文件的各种信息。

以下是和file对象相关的所有属性的列表：

| 属性             | 描述                                      |
| -------------- | --------------------------------------- |
| file.closed    | 返回true如果文件已被关闭，否则返回false。               |
| file.mode      | 返回被打开文件的访问模式。                           |
| file.name      | 返回文件的名称。                                |
| file.softspace | 如果用print输出后，必须跟一个空格符，则返回false。否则返回true。 |

如下实例：

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 打开一个文件
fo = open("foo.txt", "wb")
print "文件名: ", fo.name
print "是否已关闭 : ", fo.closed
print "访问模式 : ", fo.mode
print "末尾是否强制加空格 : ", fo.softspace
```

以上实例输出结果：

```
文件名:  foo.txt
是否已关闭 :  False
访问模式 :  wb
末尾是否强制加空格 :  0
```

### close()方法

File 对象的 close（）方法刷新缓冲区里任何还没写入的信息，并关闭该文件，这之后便不能再进行写入。

当一个文件对象的引用被重新指定给另一个文件时，Python 会关闭之前的文件。用 close（）方法关闭文件是一个很好的习惯。

语法：

```
fileObject.close();
```

例子：

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 打开一个文件
fo = open("foo.txt", "wb")
print "文件名: ", fo.name
 
# 关闭打开的文件
fo.close()
```

以上实例输出结果：

```
文件名:  foo.txt
```

读写文件：

file对象提供了一系列方法，能让我们的文件访问更轻松。来看看如何使用read()和write()方法来读取和写入文件。

### write()方法

write()方法可将任何字符串写入一个打开的文件。需要重点注意的是，Python字符串可以是二进制数据，而不是仅仅是文字。

write()方法不会在字符串的结尾添加换行符('\n')：

语法：

```
fileObject.write(string);
```

在这里，被传递的参数是要写入到已打开文件的内容。

例子：

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 打开一个文件
fo = open("foo.txt", "wb")
fo.write( "www.runoob.com!\nVery good site!\n");
 
# 关闭打开的文件
fo.close()
```

上述方法会创建foo.txt文件，并将收到的内容写入该文件，并最终关闭文件。如果你打开这个文件，将看到以下内容:

```
$ cat foo.txt 
www.runoob.com!
Very good site!
```

### read()方法

read（）方法从一个打开的文件中读取一个字符串。需要重点注意的是，Python字符串可以是二进制数据，而不是仅仅是文字。

语法：

```
fileObject.read([count]);
```

在这里，被传递的参数是要从已打开文件中读取的字节计数。该方法从文件的开头开始读入，如果没有传入count，它会尝试尽可能多地读取更多的内容，很可能是直到文件的末尾。

### 例子：

这里我们用到以上创建的 foo.txt 文件。

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 打开一个文件
fo = open("foo.txt", "r+")
str = fo.read(10);
print "读取的字符串是 : ", str
# 关闭打开的文件
fo.close()
```

以上实例输出结果：

```
读取的字符串是 :  www.runoob
```

文件位置：

------

## 文件定位

tell()方法告诉你文件内的当前位置；换句话说，下一次的读写会发生在文件开头这么多字节之后。

seek（offset [,from]）方法改变当前文件的位置。Offset变量表示要移动的字节数。From变量指定开始移动字节的参考位置。

如果from被设为0，这意味着将文件的开头作为移动字节的参考位置。如果设为1，则使用当前的位置作为参考位置。如果它被设为2，那么该文件的末尾将作为参考位置。

例子：

就用我们上面创建的文件foo.txt。

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 打开一个文件
fo = open("foo.txt", "r+")
str = fo.read(10);
print "读取的字符串是 : ", str
 
# 查找当前位置
position = fo.tell();
print "当前文件位置 : ", position
 
# 把指针再次重新定位到文件开头
position = fo.seek(0, 0);
str = fo.read(10);
print "重新读取字符串 : ", str
# 关闭打开的文件
fo.close()
```

以上实例输出结果：

```
读取的字符串是 :  www.runoob
当前文件位置 :  10
重新读取字符串 :  www.runoob
```

## 重命名和删除文件

Python的os模块提供了帮你执行文件处理操作的方法，比如重命名和删除文件。

要使用这个模块，你必须先导入它，然后才可以调用相关的各种功能。

rename()方法：

rename()方法需要两个参数，当前的文件名和新文件名。

语法：

```
os.rename(current_file_name, new_file_name)
```

例子：

下例将重命名一个已经存在的文件test1.txt。

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import os
 
# 重命名文件test1.txt到test2.txt。
os.rename( "test1.txt", "test2.txt" )
```

### remove()方法

你可以用remove()方法删除文件，需要提供要删除的文件名作为参数。

语法：

```
os.remove(file_name)
```

例子：

下例将删除一个已经存在的文件test2.txt。

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import os
 
# 删除一个已经存在的文件test2.txt
os.remove("test2.txt")
```

### Python里的目录：

所有文件都包含在各个不同的目录下，不过Python也能轻松处理。os模块有许多方法能帮你创建，删除和更改目录。

#### mkdir()方法

可以使用os模块的mkdir()方法在当前目录下创建新的目录们。你需要提供一个包含了要创建的目录名称的参数。

语法：

```
os.mkdir("newdir")
```

例子：

下例将在当前目录下创建一个新目录test。

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import os
 
# 创建目录test
os.mkdir("test")
```

#### chdir()方法

可以用chdir()方法来改变当前的目录。chdir()方法需要的一个参数是你想设成当前目录的目录名称。

语法：

```
os.chdir("newdir")
```

例子：

下例将进入"/home/newdir"目录。

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import os
 
# 将当前目录改为"/home/newdir"
os.chdir("/home/newdir")
```

getcwd()方法：

getcwd()方法显示当前的工作目录。

语法：

```
os.getcwd()
```

例子：

下例给出当前目录：

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import os
 
# 给出当前的目录
os.getcwd()
```

#### rmdir()方法

rmdir()方法删除目录，目录名称以参数传递。

在删除这个目录之前，它的所有内容应该先被清除。

语法：

```
os.rmdir('dirname')
```

例子：

以下是删除" /tmp/test"目录的例子。目录的完全合规的名称必须被给出，否则会在当前目录下搜索该目录。

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import os
 
# 删除”/tmp/test”目录
os.rmdir( "/tmp/test"  )
```

### 文件、目录相关的方法

三个重要的方法来源能对Windows和Unix操作系统上的文件及目录进行一个广泛且实用的处理及操控，如下：

* [File 对象方法](http://www.runoob.com/python/file-methods.html): file对象提供了操作文件的一系列方法。
* [OS 对象方法](http://www.runoob.com/python/os-file-methods.html): 提供了处理文件及目录的一系列方法。

### Python File(文件) 方法

file 对象使用 open 函数来创建，下表列出了 file 对象常用的函数：

| 序号   | 方法及描述                                    |
| ---- | ---------------------------------------- |
| 1    | [file.close()](http://www.runoob.com/python/file-close.html)关闭文件。关闭后文件不能再进行读写操作。 |
| 2    | [file.flush()](http://www.runoob.com/python/file-flush.html)刷新文件内部缓冲，直接把内部缓冲区的数据立刻写入文件, 而不是被动的等待输出缓冲区写入。 |
| 3    | [file.fileno()](http://www.runoob.com/python/file-fileno.html)返回一个整型的文件描述符(file descriptor FD 整型), 可以用在如os模块的read方法等一些底层操作上。 |
| 4    | [file.isatty()](http://www.runoob.com/python/file-isatty.html)如果文件连接到一个终端设备返回 True，否则返回 False。 |
| 5    | [file.next()](http://www.runoob.com/python/file-next.html)返回文件下一行。 |
| 6    | [file.read([size\])](http://www.runoob.com/python/python-file-read.html)从文件读取指定的字节数，如果未给定或为负则读取所有。 |
| 7    | [file.readline([size\])](http://www.runoob.com/python/file-readline.html)读取整行，包括 "\n" 字符。 |
| 8    | [file.readlines([sizehint\])](http://www.runoob.com/python/file-readlines.html)读取所有行并返回列表，若给定sizeint>0，返回总和大约为sizeint字节的行, 实际读取值可能比sizhint较大, 因为需要填充缓冲区。 |
| 9    | [file.seek(offset[, whence\])](http://www.runoob.com/python/file-seek.html)设置文件当前位置 |
| 10   | [file.tell()](http://www.runoob.com/python/file-tell.html)返回文件当前位置。 |
| 11   | [file.truncate([size\])](http://www.runoob.com/python/file-truncate.html)截取文件，截取的字节通过size指定，默认为当前文件位置。 |
| 12   | [file.write(str)](http://www.runoob.com/python/python-file-write.html)将字符串写入文件，没有返回值。 |
| 13   | [file.writelines(sequence)](http://www.runoob.com/python/file-writelines.html)向文件写入一个序列字符串列表，如果需要换行则要自己加入每行的换行符。 |

## Python 异常处理

python提供了两个非常重要的功能来处理python程序在运行中出现的异常和错误。你可以使用该功能来调试python程序。

* 异常处理: 本站Python教程会具体介绍。
* 断言(Assertions):本站Python教程会具体介绍。

------

### python标准异常

| 异常名称                      | 描述                                |
| ------------------------- | --------------------------------- |
| BaseException             | 所有异常的基类                           |
| SystemExit                | 解释器请求退出                           |
| KeyboardInterrupt         | 用户中断执行(通常是输入^C)                   |
| Exception                 | 常规错误的基类                           |
| StopIteration             | 迭代器没有更多的值                         |
| GeneratorExit             | 生成器(generator)发生异常来通知退出           |
| StandardError             | 所有的内建标准异常的基类                      |
| ArithmeticError           | 所有数值计算错误的基类                       |
| FloatingPointError        | 浮点计算错误                            |
| OverflowError             | 数值运算超出最大限制                        |
| ZeroDivisionError         | 除(或取模)零 (所有数据类型)                  |
| AssertionError            | 断言语句失败                            |
| AttributeError            | 对象没有这个属性                          |
| EOFError                  | 没有内建输入,到达EOF 标记                   |
| EnvironmentError          | 操作系统错误的基类                         |
| IOError                   | 输入/输出操作失败                         |
| OSError                   | 操作系统错误                            |
| WindowsError              | 系统调用失败                            |
| ImportError               | 导入模块/对象失败                         |
| LookupError               | 无效数据查询的基类                         |
| IndexError                | 序列中没有此索引(index)                   |
| KeyError                  | 映射中没有这个键                          |
| MemoryError               | 内存溢出错误(对于Python 解释器不是致命的)         |
| NameError                 | 未声明/初始化对象 (没有属性)                  |
| UnboundLocalError         | 访问未初始化的本地变量                       |
| ReferenceError            | 弱引用(Weak reference)试图访问已经垃圾回收了的对象 |
| RuntimeError              | 一般的运行时错误                          |
| NotImplementedError       | 尚未实现的方法                           |
| SyntaxError               | Python 语法错误                       |
| IndentationError          | 缩进错误                              |
| TabError                  | Tab 和空格混用                         |
| SystemError               | 一般的解释器系统错误                        |
| TypeError                 | 对类型无效的操作                          |
| ValueError                | 传入无效的参数                           |
| UnicodeError              | Unicode 相关的错误                     |
| UnicodeDecodeError        | Unicode 解码时的错误                    |
| UnicodeEncodeError        | Unicode 编码时错误                     |
| UnicodeTranslateError     | Unicode 转换时错误                     |
| Warning                   | 警告的基类                             |
| DeprecationWarning        | 关于被弃用的特征的警告                       |
| FutureWarning             | 关于构造将来语义会有改变的警告                   |
| OverflowWarning           | 旧的关于自动提升为长整型(long)的警告             |
| PendingDeprecationWarning | 关于特性将会被废弃的警告                      |
| RuntimeWarning            | 可疑的运行时行为(runtime behavior)的警告     |
| SyntaxWarning             | 可疑的语法的警告                          |
| UserWarning               | 用户代码生成的警告                         |

### 什么是异常？

异常即是一个事件，该事件会在程序执行过程中发生，影响了程序的正常执行。

一般情况下，在Python无法正常处理程序时就会发生一个异常。

异常是Python对象，表示一个错误。

当Python脚本发生异常时我们需要捕获处理它，否则程序会终止执行。

------

### 异常处理

捕捉异常可以使用try/except语句。

try/except语句用来检测try语句块中的错误，从而让except语句捕获异常信息并处理。

如果你不想在异常发生时结束你的程序，只需在try里捕获它。

语法：

以下为简单的*try....except...else*的语法：

```python
try:
<语句>        #运行别的代码
except <名字>：
<语句>        #如果在try部份引发了'name'异常
except <名字>，<数据>:
<语句>        #如果引发了'name'异常，获得附加的数据
else:
<语句>        #如果没有异常发生
```

```python
try:
    正常的操作
   ......................
except:
    发生异常，执行这块代码
   ......................
else:
    如果没有异常执行这块代码
```

```python
try:
    正常的操作
   ......................
except(Exception1[, Exception2[,...ExceptionN]]]):
   发生以上多个异常中的一个，执行这块代码
   ......................
else:
    如果没有异常执行这块代码
```

```python
try:
<语句>
finally:
<语句>    #退出try时总会执行
raise
```

### 用户自定义异常

通过创建一个新的异常类，程序可以命名它们自己的异常。异常应该是典型的继承自Exception类，通过直接或间接的方式。

以下为与RuntimeError相关的实例,实例中创建了一个类，基类为RuntimeError，用于在异常触发时输出更多的信息。

在try语句块中，用户自定义的异常后执行except块语句，变量 e 是用于创建Networkerror类的实例。

```python
class Networkerror(RuntimeError):
    def __init__(self, arg):
        self.args = arg
```

在你定义以上类后，你可以触发该异常，如下所示：

```python
try:
    raise Networkerror("Bad hostname")
except Networkerror,e:
    print e.args
```

## 操作符重载

| 函数                                       | 作用                                       |
| ---------------------------------------- | ---------------------------------------- |
| ```__call__                              | 定义了__call__方法的类实例，可以像一个函数一样被“调用”         |
| ```__str__                               | 类似于[Java](http://lib.csdn.net/base/javaee)对象的toString()方法 |
| ```__init__,__del__                      | 初始化函数和构造函数                               |
| ```__eq__,__ne__,__lt__,__le__,__gt__,__ge__ | ==,!=,<,<=,>,>=                          |
| ```__getitem__                           | 使用 x[i]索引操作符                             |
| ```__len__                               | 对序列对象使用len()                             |
| ```__contains__                          | 测试是否包含某个元素                               |