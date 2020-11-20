[Tech For Fun](http://kaelzhang81.github.io/)

#### IDEA
  * 避免import *
    File -> setting -> Editor -> Code Style -> Java -> Imports  
    这两项设置高一点  
    Class count to use import with '*'  
    &  
    Names count to use static import with '*'
  * 自动删除无用import包  
    File --> Settings... --> Editor --> General --> Auto Import --> 勾选"Optimize imports on the fly(for current project)"

#### 文件上传可能引起xxe攻击
  * Excel文件  
    旧的是XLS，新的是SLSX  
    Excel文件的扩展名为XLSX。 这是Microsoft开发的一种开放文件格式; 在幕后它是一个包含多个XML文件的zip文件。  
    [文件上传功能可能存在XXE](https://blog.csdn.net/qq_36093477/article/details/82849631)
