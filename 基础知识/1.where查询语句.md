# 查询语句总结
语法如下：
```
select 查询列表    ⑦
from 表1 别名       ①
连接类型 join 表2   ②
on 连接条件         ③
where 筛选          ④
group by 分组列表   ⑤
having 筛选         ⑥
order by排序列表    ⑧
limit 起始条目索引，条目数;  ⑨
```

## where语句
语法如下：
```
select 查询列表 from 表1 (别名) where 筛选条件;
```
#### 1.操作符说明

<font size=1>
  
|操作符|说明|
| :------: | :------: |
|=|等于|
|<>|不等于|
|!=|不等于|
|<|小于|
|<=|小于等于|
|>|大于|
|>=|大于等于|
|BETWEEN … AND … |在指定的两个值之间|
| IS NULL | 检查空值 |
|IN(…,…,…)|匹配括号内的任意值|
|NOT|取反|
  
</font>

#### 2.多个where子句同时查询
> <font size=1> 有2种方式可使用
> <br>①以AND子句的方式；②以OR子句的方式</br>
> 若AND和OR同时存在1条sql语句中，那优先处理AND语句，再处理OR语句。可以通过加上()括号来解决这个问题</font>

语法如下：
```
select 查询列表
from 表1 (别名) 
where 筛选条件1 AND 筛选条件2;

select 查询列表
from 表1 (别名) 
where 筛选条件1 OR 筛选条件2;
```

#### 3.where与in的搭配
> in的作用：指定条件范围，范围内的每个条件都可以进行匹配；实际作用与or相似
> 优点：①更直观；②更容易管理；③比or执行更快；④可以包括其他select语句(★）

语法：
```
select 查询列表
from 表1 (别名) 
where 筛选项 in（…,…,…）;
```

#### 4.where与NOT的搭配
> NOT的作用：否认它之后所跟的任何条件，支持对IN、BETWEEN、EXISTS子句取反
语法：
```
select 查询列表
from 表1 (别名) 
where 筛选项 NOT in（…,…,…）;
```
