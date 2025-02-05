
## 1，JDBC概述 
### 1.1  JDBC概念
   JDBC   就是使用Java语言操作关系型数据库的一套API
   全称：( Java DataBase Connectivity ) Java 数据库连接
   
   我们开发的同一套Java代码是无法操作不同的关系型数据库，因为每一个关系型数据库的底层实现细节都不一样。如果这样，问题就很大了，在公司中可以在开发阶段使用的是MySQL数据库，而上线时公司最终选用oracle数据库，我们就需要对代码进行大批量修改，这显然并不是我们想看到的。我们要做到的是同一套Java代码操作不同的关系型数据库，而此时sun公司就指定了一套标准接口（JDBC），JDBC中定义了所有操作关系型数据库的规则。众所周知接口是无法直接使用的，我们需要使用接口的实现类，而这套实现类（称之为：驱动）就由各自的数据库厂商给出。
   
### 1.2  JDBC本质

* 官方（sun公司）定义的一套操作所有关系型数据库的规则，即接口
* 各个数据库厂商去实现这套接口，提供数据库驱动jar包
* 我们可以使用这套接口（JDBC）编程，真正执行的代码是驱动jar包中的实现类
![](https://raw.githubusercontent.com/Gg-Maker6/note_img/main/Pasted%20image%2020250121203003.png)
### 1.3  JDBC好处

* 各数据库厂商使用相同的接口，Java代码不需要针对不同数据库分别开发
* 可随时替换底层数据库，访问数据库的Java代码基本不变

以后编写操作数据库的代码只需要面向JDBC（接口），操作哪儿个关系型数据库就需要导入该数据库的驱动包，如需要操作MySQL数据库，就需要再项目中导入MySQL数据库的驱动包。
## 2，JDBC快速入门
通过Java操作数据库的流程
![](https://raw.githubusercontent.com/Gg-Maker6/note_img/main/Pasted%20image%20jdbc2.png)

![](https://raw.githubusercontent.com/Gg-Maker6/note_img/main/Pasted%20image%2020250121203033.png)

### 0：导入jar包
	创建dictionary lib 拷贝驱动包
	右击驱动包 选择 add as library
![](https://raw.githubusercontent.com/Gg-Maker6/note_img/main/Pasted%20image%2020250121203049.png)

### 1.注册驱动
![](https://raw.githubusercontent.com/Gg-Maker6/note_img/main/Pasted%20image%2020250121203058.png)
### 2.获取连接
![](https://raw.githubusercontent.com/Gg-Maker6/note_img/main/Pasted%20image%2020250121203107.png)

URL：指定数据库
user：同户名
password：密码

### 3.定义sql语句

### 4.获取执行sql对象
![](https://raw.githubusercontent.com/Gg-Maker6/note_img/main/Pasted%20image%2020250121203115.png)
### 5.执行sql
![](https://raw.githubusercontent.com/Gg-Maker6/note_img/main/Pasted%20image%2020250121203121.png)
### 6.处理结果
### 7.释放资源
