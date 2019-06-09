# JDBC

> Java数据库连接，（Java Database Connectivity，简称JDBC）是Java语言中用来规范客户端程序如何来访问数据库的应用程序接口，提供了诸如查询和更新数据库中数据的方法。JDBC也是Sun Microsystems的商标。JDBC是面向关系型数据库的。
>
> **JDBC 就是sun 公司 规定的一个规范接口**





## JDBC 使用

1. 加载驱动(注册驱动)
2. 链接数据库
3. 访问数据库
4. 执行SQL

```java

import java.sql.*;
class Test{
    static final String JDBC_DRIVER = "com.mysql.jdbc.Driver";//驱动名称
    static final String JDBC_URL ="jdbc:mysql://127.0.0.1:3306/databasename";//数据库URL 和数据库名
    public static void main(String[] args){
       Connection conn = null;
       Statement st = null;
         try{
            //加载驱动
            class.forName(JDBC_DRIVER);
            //连接数据库,(url,用户名,密码)
            conn = DriverManager.getConnection(JDBC_URL,'user','pass');
            
            //访问数据库
            st = conn.createStatement();
            // 执行SQL
            
            ResultSet rs = st.excuteQuery(SQL);
            while(rs.next()){
                rs.getInt("id");
            }
        }catch{SQLException e}{
            //出来jdbc错误
            e.printStackTrace();
        }catch(Exception e){
            //数量class.forName异常
            e.printStackTrace();
        }finally{
            try{
                //关闭资源
                if(st != null) st.close();
            }catch(SQLException e){
                e.printStackTrace();
            }
            try{
                if(conn != null) conn.close();
            }catch(SQLException e){
                e.printStackTrace();
            }
        }
    }
}

```

