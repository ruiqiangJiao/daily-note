# python
---

## 时间处理

1 **dateutil** 

```{python}
import datetime
from dateutil import rrule
today = datetime.date.today()
oneday = datetime.date(2017,10 ,17)
years = rrule.rrule(rrule.YEARLY, dtstart=oneday, until=today).count()
months = rrule.rrule(rrule.MONTHLY, dtstart=oneday, until=today).count()
days = rrule.rrule(rrule.DAILY, dtstart=oneday, until=today).count()
print years
print months
print days
```

2 **pandas** 

```{python}
import pandas as pd 
import datetime , time
now = datetime.datetime.now()
ago = now - pd.tseries.offsets.DateOffset(months = 4)
print ago
```


3 **time**

计算机使用时间戳和**struct_time**数组两种方式表示时间

```{python}
import time
print(time.localtime(time.time()))
```

格式字符串中可以使用的日期和时间符号如下:

+ %y 两位数的年份表示（00-99）;

+ %Y 四位数的年份表示 （000 - 9999）;

+ %m 月份（01-12）;

+ %d 月内中一天（0-31）;

+ %H 24小时制小时数（0-23）;

+ %I 12小时制小时数（01-12）;

+ %M 分钟数（00~59）;

+ %j 年内的一天;

+ %U 一年中的星期数（00~53），星期天为星期的开始;

+ %w 星期（0~6），星期天为星期的开始;

+ %W 一年中的星期数（00~53），星期一位星期的开始.


## 面向对象

### 面向对象基本概念

(1) 继承

(2) 多态

(3) 封装

(4) 构造函数

当创建类的对象实例时系统会自动调用构造函数，通过构造函数对类进行初始化操作。

(5) 析构函数

释放类占用的资源。


(6) 静态成员

静态变量和静态方法与类具体的对象没有关系，而只属于他们定义的类。在静态方法无法访问实例变量，不可以直接访问类的静态变量，但可以通过类名引用静态变量。

```{python}
class UserInfo:
  def __init__(self , name , pwd):
    self.username = name
    self._pwd = pwd
    
  def output(self):
    print("username" ,  self.username) 
    
  def __del__(self):
    print("byebye~")
    
u = UserInfo("admin" , "123456")
u.output()
del u
```

## 正则表达式

- []: 匹配方括号中任意一个内容

- ^ : 匹配以某个内容开头的模式

- $ : 匹配以某个内容开头的模式

```{python}
import re
pattern = r'[0-9]'
print re.findall(pattern , '您好, jony is culcating 1+1') 
pattern = r'^h'
print re.findall(pattern , 'hello world') 
```

