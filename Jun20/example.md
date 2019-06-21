Java读写Properties配置文件

1.启动数据库

通过 计算机管理>服务> MySQL>启动

2.修改使用properties配置文件来 记录 数据库 驱动名、数据库名、账号、密码的信息（https://blog.csdn.net/wenhaowang/article/details/8494500）

```java
InputStream in = getClass().getResourceAsStream("db.properties");
Properties pro = new Properties();
 pro.load(in);
String  username = pro.getProperty("username").trim();
String  password = pro.getProperty("password").trim();
String  url = pro.getProperty("url").trim();
String  driver = pro.getProperty("driver").trim();
```

