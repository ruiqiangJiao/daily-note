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

## 正则表达式

## 分组排序

```python
df = pd.DataFrame({'Sp':['a','b','c','d','e','f'], 'Mt':['s1', 's1', 's2','s2','s2','s3'], 'Value':[1,2,3,4,5,6], 'Count':[3,2,5,10,10,6]})
df
```

|    | Sp | Mt | Value | Count |
|----|----|----|-------|-------|
|0   | a  | s1 | 1     | 3     |
|1   | b  | s1 | 2     | 2     |
|2   | c  | s2 | 3     | 5     |
|3   | d  | s2 | 4     | 10    |
|4   | e  | s2 | 5     | 10    |
|5   | f  | s3 | 6     | 6     |

```python
df.sort_values('Count', ascending=False).groupby('Mt', as_index=False).first()
```

|    | Mt | Sp | Value | Count |
|----|----|----|-------|-------|
|0   | s1 | a  | 1     | 3     |
|1   | s2 | d  | 4     | 10    |
|2   | s3 | f  | 6     | 6     |

## 同一个组进行合并

```python
series = df.groupby(by='Mt',as_index=True).apply(lambda p:[','.join(p['Sp'])])
df_result = pd.DataFrame({'Mt':series.index, 'Sp': series.values})
df_result
```

|    | Mt | Sp       |
|----|----|----------|
|0   | s1 | [a, b]   |
|1   | s2 | [c, d, e]|
|2   | s3 | [f]      |


## 常用包说明文档

[pandarallel](https://github.com/nalepae/pandarallel)

[paratext](https://github.com/wiseio/paratext)

[xgboost](https://xgboost.readthedocs.io/en/latest/python/python_api.html)

##  参考资料

[Python数据分析](https://seancheney.gitbook.io/python-for-data-analysis-2nd/di-10-zhang-shu-ju-ju-he-yu-fen-zu-yun-suan)

[颜色色卡](https://www.colorhexa.com/)

[Matplotlib可视化最有价值的 50 个图表](http://liyangbit.com/pythonvisualization/matplotlib-top-50-visualizations/#)