---
typora-root-url: ..\asset
---

![httpStudy](/httpStudy.PNG)



httpStudy

```java
public class httpStudy extends HttpServlet {
    public void doGet(HttpServletRequest req, HttpServletResponse resp)
        {
        System.out.println("get is running");
    }
    public void doPost(HttpServletRequest req,HttpServletResponse resp)
       {
        System.out.println("post is running  "+"username:"+ req.getParameter("username"));
    }

    public static void main(String[] args) {
        System.out.println("hello");
    }
}
```



web.xml

```xml
<servlet>
            <servlet-name>httpStudy</servlet-name>
            <servlet-class>com.victor.httpStudy</servlet-class>
        </servlet>
        <servlet-mapping>
            <servlet-name>httpStudy</servlet-name>
            <url-pattern>/test</url-pattern>
        </servlet-mapping>
```



index.jsp

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
  <head>
    <title>test</title>
  </head>
  <body>
  <a href="/test">超链接test</a>
  <form action="/test" name="" method="post">
    <input type="text" name="username" style="width: 100px;">
    <input value="提交" type="submit"/>
  </form>
  </body>
</html>
```

