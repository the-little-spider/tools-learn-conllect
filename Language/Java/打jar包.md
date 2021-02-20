最简单的jar包——直接输出hello  
（1）用记事本写一个Hello.java的文件
```
class Hello{
     public static void main(String[] agrs){
         System.out.println("hello");
     }
 }
```
（2）用命令行进入到该目录下，编译这个文件

　　 javac Hello.java 

（3）将编译后的Hello.class文件打成jar包

　　 jar -cvf hello.jar Hello.class 

　　c表示要创建一个新的jar包，v表示创建的过程中在控制台输出创建过程的一些信息，f表示给生成的jar包命名

（4）运行jar包

　　 java -jar hello.jar  这时会报如下错误  hello.jar中没有主清单属性 

　　添加Main-Class属性

　　用压缩软件打开hello.jar，会发现里面多了一个META-INF文件夹，里面有一个MENIFEST.MF的文件，用记事本打开
  ```
  Manifest-Version: 1.0
  Created-By: 1.8.0_121 (Oracle Corporation)
  ```
  在第三行的位置写入 Main-Class: Hello （注意冒号后面有一个空格，整个文件最后有一行空行），保存

  再次运行 java -jar hello.jar ，此时成功在控制台看到  hello ，成功
