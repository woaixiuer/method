```
driverClassName = com.mysql.cj.jdbc.Driver
url=jdbc:mysql://localhost:3306/day23
username=root
password=133qweASD
#??????
initialSize = 5
#?????
maxActive = 10
#??????
maxWait = 3000
```

必须这样才能使用druid连上数据库，下面那样写连不上，版本问题

```
driverClassName=com.mysql.jdbc.Driver
url=jdbc:mysql://localhost:3306/day23
username=root
password=133qweASD
initialSize=5
maxActive=10
maxWait=3000
```

