# ***第一天***

# 这是一个段落


香蕉派

banana

## 这是第二个段落

苹果派
>***错的不是我，错的是这个世界***.

[百度脑图](http://naotu.baidu.com) - 控制创意，如此简单
[BILIBILI](https://www.bilibili.com/)
+ 首先
+ 其次
+ 最后
* 第一，...
* 第二，...
* 第三，...


1. 打开冰箱
  1. 用右手打开
  2. 轻轻地打开
2. 把大象放进去
* 不要吐槽
  * 大象太大
  * 冰箱太小
  * 例子很无聊
3. 关上冰箱

|月份|收入|支出|
|:-:|:-:|:-:|
|8|1000|500|
|9|1200|600|
|10|1400|650|

现在你可以不用 `document.getElementById()` 了，现代浏览器都把复制了 `id` 属性的元素放在了
全局变量里。
aaaaa



~~我被删除了~~
September 16, 2019 1:36 AMSeptember 16, 2019 1:36 AM

# ***学习使用git的第二天***


我在与`git pro`艰难地搏斗后彻底放弃

求助后转战[***张雪峰的git教程***](https://www.liaoxuefeng.com/wiki/896043488029600/896827951938304)

但是我发现.....还是有很多git的代码的意义啥的没说

张雪峰直接给出了

> $ mkdir learngit<br>
  $ cd learngit<br>
  $ pwd<br>
 /Users/michael/learngit

说这样就可以创建版本库

**but**    这样我一点都不安心啊

于是乎我去找到了别人做的[*git的命令总结*](https://www.cnblogs.com/chris0710/p/8925977.html)

> $ cd:e // 切换盘符<br>
 $ cd .. // 回到文件上一层(注: cd与..中间有个空格)<br>
 $ cd ~ // 回到当前目录的主目录<br>
 $ cd 文件夹名 //去到当前目录内的叫该名的文件夹<br>
 $ mkdir Git // 创建文件夹Git<br>
 $ pwd // 显示当前路径/e/Git/learngit<br>
 $ git log //查看现在版本库的状态<br>
 $ cat .xxx // 查看当前文件（xxx）所有配置信息（包括别名信息)
 <br />
 
![image](https://github.com/blacksadnb/daily-record/blob/master/abc.png)

<hr><hr />
<font size="4px">
	
***这是分界线***
<!--
我还不会把文字插入在水平分界线的中间，有待学习
-->
晚上去听c的讲座，关键词大概就是：黑盒抽象，编译器，ide，占位符
	
觉得在学第一门编程语言之前先要简明地弄明白计算机的工作原理之类的

</font>

+ 二进制最稳定以及二极管的通电特性，所以电脑用二进制
+ 位，就是数字抽象的基本单元
+ 进位，是为了把无限分为有限分而治之。
+  二极管构成逻辑门，逻辑门构成逻辑电路，逻辑电路组成了cpu进行计算。
+ 高级编程语言如c，python是为了人性化而设计的
+ 编译器负责把人性化的编程代码转化成为计算机能通过二进制数字来理解的机械语言
+ c语言的运行速度快的特性大概就因为从c语言编写的代码转译成机械代码的算法更简单，花的时间更少吧？

<hr/>

好了，开始继续学git的使用orz

直接用微软记事本来编辑readme.txt的话，在git diff时无法识别文件修改前后的差别

大概是git不支持[***BOM***](https://www.cnblogs.com/shgq/p/3927255.html)吧，换用notepad++的utf-8 without BOM后解决了问题

在Git中，用HEAD表示当前版本.上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100

<font color="#ad9" size="5px">
	
# ***第三天***
</font>

工作区就是有.git文件夹的地方

.git文件夹内是版本库（版本库包含staged暂存区和branch分支）

git add是把文件加入暂存区

git commit是把暂存区文件提交到分支branch

发现了一个解决git rm问题的好网站https://stackoverflow.com/questions/2125710/how-to-revert-a-git-rm-r

所以用git rm不光会删除工作区的文件，还会破坏index

而使用rm删除工作去的文件不会破坏index，所以可以直接用git checkout -- xxx恢复

破坏了index后只能回溯版本用git reset head，回到最新的版本库（只要git rm后没commit更新head）

如果reset之前缓存区有important的待提交的changes，使用git stash可以save your uncommited changes

```
git stash 
git reset --hard
git stash pop
```

>working tree：就是你所工作在的目录，每当你在代码中进行了修改，working tree的状态就改变了。
index file：是索引文件，它是连接working tree和commit的桥梁，每当我们使用git-add命令来登记后，index file的内容就改变了，此时index file就和working tree同步了。
commit：是最后的阶段，只有commit了，我们的代码才真正进入了git仓库。我们使用git-commit就是将index file里的内容提交到commit中。
总结一下：
git diff：是查看working tree与index file的差别的。
git diff --cached：是查看index file与commit的差别的。
git diff HEAD：是查看working tree和commit的差别的，在这里HEAD代表的是最近的一次commit的信息。
![git中3大区关系](https://img-blog.csdn.net/20180302162826778)
版权声明：本文为CSDN博主「生活因我绚丽」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/heart_mine/article/details/79424591

### 我有一个猜测

我在输入git reset sss.txt时出现了Use '--' to separate filenames from revisions，like this：```git <command> [<revision>...] -- [<file>...]```

而用git reset -- sss.txt时很顺利，综合搜索我知道"用`--`分割文件名和版本号"，所以是否用了`--`但不输入版本号就默认head了呢，所以我输入git reset -- sss.txt时不会出现错误。

在进一步学习后，其实git reset head sss.txt与上面功能相同，只要能让git区分即可

更进一步地git reset学习请入https://www.cnblogs.com/kidsitcn/p/4513297.html

另外，在我删除了几个无关文件并commit后，想要git push origin master，却因为远程仓库文件id数与本地commit中不一致导致无法提交，最后使用git pull --rebase origin master以本地commit为base，再融合了origin master的本地所未有的文件后成功地push进origin。

git pull = git fetch + git merge
git pull --rebase = git fetch + git rebase

关于rebase和merge的不同，可以求助此网站https://blog.csdn.net/dake_160413/article/details/78676163


