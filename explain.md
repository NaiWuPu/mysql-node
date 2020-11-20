### explain 用法
```sql
explain select * FROM TABLE_NAME ;
```
### ID 说明
```null
ID 相同 ，执行顺序由上而下
ID 不同，如果是子查询 ID序号会递增 ID 值越大优先级越高 越先被执行
有相同也有不同
ID如果相同可以认为是一组，从上往下顺序执行，在所有组中，ID 越大，优先级越高，约先执行衍生
= DERICED
```

### select_type 说明
```null
SIMPLE 简单的select 查询，查询中不包含子查询或者UNION
PRIMARY 查询中若包括任何复杂的字部份，最外层查询则被标记
SUBQUERY 在SELECT或者 WHERE列表中包含子查询
DERIVED 在FROM列表中包含的子查询责备标记位DERICED（衍生） MYSQL会递归执行这些子查询，把结果放在临时表里
UNION 在第二个SELECT 出现UNION之后，则被标记位UNION；若UNION包含在FROM子句的子查询中，外层SELECT将被标记位DERIVED
```

### type 说明
```null
访问类型排列
显示查询使用了何种类型
system>const>eq_ref>ref>range>index>ALL
```