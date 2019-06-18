## 1.概念

MySQL 为关系型数据库(Relational Database Management System), 这种所谓的”关系型”可以理解为”表格”的概念, 一个关系型数据库由一个或数个表格组成。

![20171023201756830](../asset/20171023201756830.png)



数据库安装(https://baijiahao.baidu.com/s?id=1629661608981614271&wfr=spider&for=pc)

navicat链接数据库(https://jingyan.baidu.com/article/2a138328ee1345074a134f8d.html)

navicat增删改查(https://blog.csdn.net/sisure_shen/article/details/81042254)

查询

select * from hello(表名) where name='Amy';



idea连接数据库(https://blog.csdn.net/qq_27093465/article/details/52872582)



navicat修改后 idea显示修改内容

idea修改后，右键submit提交可在navicat中看到更新信息



#### jdbc驱动连接数据库并传值

- 传入固定数据的时候，使用单个字符串，并且用引号引起来

  // String sql = "INSERT into hello(id,userName,age,comment) VALUES ('10','a','3','123')";

```java
public class connection {
    public void insertDataByPreparedStatement(user user0) throws InstantiationException, IllegalAccessException, ClassNotFoundException, SQLException{
        String driver="com.mysql.jdbc.Driver";
        //这里我的数据库是cxxt
        String url="jdbc:mysql://localhost:3306/test01";
        String username = "root";
        String password = "admin";
        Statement stmt = null;
        Connection connection = null;
        //在此处对字符串进行拼接
        String sql = "insert into hello(id,userName,age,comment)"
                + " values( "+"'"+user0.getId()+"'"
                +",'"+user0.getUserName()+"'"
                +",'"+user0.getAge()+"'"
                +",'"+user0.getComment()+"')";
       
        System.out.println("接接后的sql语句:"+sql);
        System.out.println("开始执行JDBC操作");
        try {
            Class.forName(driver).newInstance();/**此处加载数据库的驱动**/
            //通过DriverManager实例化数据库联接
            connection = DriverManager.getConnection(url, username, password);
            //创建Statement的对象.
            stmt = connection.createStatement();
            //执行sql语句.
            stmt.execute(sql);
        } finally {//注意,此处要处于finally的保护之下,以确保数据库联接被关闭.
            stmt.close();//关闭statement对象
            connection.close();//关闭数据库联接.
        }
        System.out.println("JDBC执行结束");

    }


    public static void main(String[] args) throws InstantiationException, IllegalAccessException, ClassNotFoundException, SQLException{
        connection jdbcParam = new connection();
        user user0 = new user();
        user0.setUserName("testname");
        user0.setComment("testcomment");
        user0.setAge(33);
        //jdbcParam.insertConcatStringData(userO);
        jdbcParam.insertDataByPreparedStatement(user0);
        
    }

}

```

