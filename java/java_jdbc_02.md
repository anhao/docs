# JDBC  完成增删改查



> 增、删、改,都是调用 `Statement` 下面的`executeUpdate(String sql)` 方法, 返回的是影响的行数
>
> 查 则调用的是` executeQuery(String sql)` 方法,返回结果集

```java
// 增、删、改
// 创建连接...
String sql = "insert into demo(`name`,`age`,`sex`) vlaues ('李四','18','男')";
int rs = stmt.executeUpdate(sql);
//关闭连接...
```

```java
//查
// 创建连接...
String sql = "select * from demo";
ResultSet rs  = stmt.executeUpdate(sql);
while(rs.next()){
    Sysotem.out.print(rs.getString("name"))
}
//关闭连接...

```

