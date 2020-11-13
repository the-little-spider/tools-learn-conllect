## tools-learn-conllect
收集一些工具和学习材料


### 先学Markdown语法  
* [Markdown 教程](https://www.runoob.com/markdown/md-tutorial.html)


### 学习Git
* <https://learngitbranching.js.org/>
* [git - 简明指南](https://rogerdudler.github.io/git-guide/index.zh.html)


  **git撤回！**
  ~~~
  git reset --hard 提交id （注意:工作空间的代码的改动就没啦）  
  如果想保留工作空间的代码只是撤销commit,请执行下面的命令:
  git reset --soft HEAD^
  HEAD^的意思是上一个版本，也可以写成HEAD~1
  如果你进行了2次commit，想都撤回，可以使用HEAD~2
  
  --mixed
  意思是：不删除工作空间改动代码，撤销commit，并且撤销git add . 操作
  这个为默认参数,git reset --mixed HEAD^ 和 git reset HEAD^ 效果是一样的。
  --soft
  不删除工作空间改动代码，撤销commit，不撤销git add .
  --hard
  删除工作空间改动代码，撤销commit，撤销git add .
  注意完成这个操作后，就恢复到了上一次的commit状态。
  ~~~
