# SQL

## 合并两个 SQL 查询

```
SELECT get.daytime, get.data as get, xh.data as xh 
        FROM ( 
                SELECT daytime, sum(get_sum) as data 
                FROM yuanbao_get 
                group by daytime 
                order by daytime 
        ) as get, 
        ( 
                SELECT daytime, sum(xh_sum) as data 
                FROM yuanbao_xh 
                group by daytime 
                order by daytime 
        ) as xh 
        where get.daytime = xh.daytime
```