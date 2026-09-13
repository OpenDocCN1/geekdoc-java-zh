
# JDBC 可调用语句–PostgreSQL 存储函数

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/jdbc/jdbc-callablestatement-postgresql-stored-function/>

一个 JDBC 的例子向你展示了如何从 PostgreSQL 数据库中调用一个存储函数。

*PS 用 PostgreSQL 11 和 Java 8 测试*

`pom.xml`

```java
 <dependency>
		<groupId>org.postgresql</groupId>
		<artifactId>postgresql</artifactId>
		<version>42.2.5</version>
	</dependency> 
```

## 1.呼叫功能

1.1 创建一个存储函数并通过 JDBC 调用它。

`FunctionReturnString.java`

```java
 package com.mkyong.jdbc.callablestatement;

import java.sql.*;

public class FunctionReturnString {

    public static void main(String[] args) {

        String createFunction = "CREATE OR REPLACE FUNCTION hello(p1 TEXT) RETURNS TEXT "
                + " AS $$ "
                + " BEGIN "
                + " RETURN 'hello ' || p1; "
                + " END; "
                + " $$ "
                + " LANGUAGE plpgsql";

        String runFunction = "{ ? = call hello( ? ) }";

        try (Connection conn = DriverManager.getConnection(
                "jdbc:postgresql://127.0.0.1:5432/test", "postgres", "password");
             Statement statement = conn.createStatement();
             CallableStatement callableStatement = conn.prepareCall(runFunction)) {

            // create or replace stored function
            statement.execute(createFunction);

            //----------------------------------

            // output
            callableStatement.registerOutParameter(1, Types.VARCHAR);

            // input
            callableStatement.setString(2, "mkyong");

            // Run hello() function
            callableStatement.executeUpdate();

            // Get result
            String result = callableStatement.getString(1);

            System.out.println(result);

        } catch (SQLException e) {
            System.err.format("SQL State: %s\n%s", e.getSQLState(), e.getMessage());
            e.printStackTrace();
        } catch (Exception e) {
            e.printStackTrace();
        }

    }
} 
```

输出

```java
 hello mkyong 
```

1.2 SQL 版本。

```java
 CREATE OR REPLACE FUNCTION hello(p1 TEXT) RETURNS TEXT 
AS $$
BEGIN
    RETURN 'hello ' || p1;
END;
$$
LANGUAGE plpgsql;

-- run it 
select hello('mkyong');
-- output: hello mkyong 
```

## 2.函数返回 SETOF

2.1 对于作为`SETOF`返回数据的函数，我们应该使用普通的`Statement`或`PreparedStatement`，而不是`CallableStatement`

*P.S 表 [`pg_roles`](http://web.archive.org/web/20230101144855/https://www.postgresql.org/docs/current/view-pg-roles.html) 是包含数据库角色*的系统表

`FunctionReturnResultSet.java`

```java
 package com.mkyong.jdbc.callablestatement;

import java.sql.*;
import java.util.ArrayList;
import java.util.List;

public class FunctionReturnResultSet {

    public static void main(String[] args) {

        List<String> users = new ArrayList<>();

        String createFunction = "CREATE OR REPLACE FUNCTION getRoles() RETURNS SETOF pg_roles "
                + " AS 'select * from pg_roles' LANGUAGE sql;";

        String runFunction = "select * from getRoles();";

        try (Connection conn = DriverManager.getConnection(
                "jdbc:postgresql://127.0.0.1:5432/test", "postgres", "password");
             Statement statement = conn.createStatement()) {

            // create a function returns as SETOF
            statement.execute(createFunction);

            // run it
            ResultSet resultSet = statement.executeQuery(runFunction);
            while (resultSet.next()) {
                users.add(resultSet.getString("rolname"));
            }

            System.out.println("Database roles...");
            users.forEach(x -> System.out.println(x));

        } catch (SQLException e) {
            System.err.format("SQL State: %s\n%s", e.getSQLState(), e.getMessage());
            e.printStackTrace();
        } catch (Exception e) {
            e.printStackTrace();
        }

    }
} 
```

输出

```java
 Database roles...
pg_signal_backend
pg_read_server_files
postgres
pg_write_server_files
pg_execute_server_program
pg_read_all_stats
pg_monitor
pg_read_all_settings
pg_stat_scan_tables 
```

2.2 SQL 版本。

```java
 CREATE OR REPLACE FUNCTION getRoles() RETURNS SETOF pg_roles 
AS 'select * from pg_roles' LANGUAGE sql;

-- run it 
select * from getRoles(); 
```

## 3.函数返回光标

3.1 JDBC +参考光标示例。

`FunctionReturnRefCursor.java`

```java
 package com.mkyong.jdbc.callablestatement;

import java.sql.*;

public class FunctionReturnRefCursor {

    public static void main(String[] args) {

        String createFunction = "CREATE OR REPLACE FUNCTION getUsers(mycurs OUT refcursor) "
                + " RETURNS refcursor "
                + " AS $$ "
                + " BEGIN "
                + "     OPEN mycurs FOR select * from pg_user; "
                + " END; "
                + " $$ "
                + " LANGUAGE plpgsql";

        String runFunction = "{? = call getUsers()}";

        try (Connection conn = DriverManager.getConnection(
                "jdbc:postgresql://127.0.0.1:5432/test", "postgres", "password");
             Statement statement = conn.createStatement();
             CallableStatement cs = conn.prepareCall(runFunction);
        ) {

            // We must be inside a transaction for cursors to work.
            conn.setAutoCommit(false);

            // create function
            statement.execute(createFunction);

            // register output
            cs.registerOutParameter(1, Types.REF_CURSOR);

            // run function
            cs.execute();

            // get refcursor and convert it to ResultSet
            ResultSet resultSet = (ResultSet) cs.getObject(1);
            while (resultSet.next()) {
                System.out.println(resultSet.getString("usename"));
                System.out.println(resultSet.getString("passwd"));
            }

        } catch (SQLException e) {
            System.err.format("SQL State: %s\n%s", e.getSQLState(), e.getMessage());
            e.printStackTrace();
        } catch (Exception e) {
            e.printStackTrace();
        }

    }
} 
```

输出–该数据库包含一个用于测试的用户🙂

```java
 postgres
******** 
```

3.2 SQL 版本。

```java
 CREATE OR REPLACE FUNCTION getUsers(mycurs OUT refcursor) RETURNS refcursor 
	AS $$
	BEGIN 
		OPEN mycurs FOR select * from pg_user;
	END;
	$$
	LANGUAGE plpgsql; 
```

## 下载源代码

`$ git clone [https://github.com/mkyong/java-jdbc.git](http://web.archive.org/web/20230101144855/https://github.com/mkyong/java-jdbc.git)`

## 参考

*   [PostgreSQL–调用存储函数](http://web.archive.org/web/20230101144855/https://jdbc.postgresql.org/documentation/94/callproc.html#callproc-resultset-refcursor)

*   [PostgreSQL–pg _ roles](http://web.archive.org/web/20230101144855/https://www.postgresql.org/docs/current/view-pg-roles.html)

*   [PostgreSQL–创建函数](http://web.archive.org/web/20230101144855/https://www.postgresql.org/docs/11/sql-createfunction.html)

*   [JDBC PL/SQL 示例](http://web.archive.org/web/20230101144855/https://docs.oracle.com/cd/A84870_01/doc/java.816/a81354/samapp2.htm)

*   [语句 JavaDocs](http://web.archive.org/web/20230101144855/https://docs.oracle.com/javase/8/docs/api/java/sql/Statement.html)

*   [Java JDBC 教程](/web/20230101144855/https://mkyong.com/tutorials/jdbc-tutorials/)

*   [PostgreSQL 11 中的新存储过程](http://web.archive.org/web/20230101144855/https://severalnines.com/blog/overview-new-stored-procedures-postgresql-11)

<input type="hidden" id="mkyong-current-postId" value="15115">
