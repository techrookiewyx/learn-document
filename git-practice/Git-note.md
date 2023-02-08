# Git   2月6日

## 配置

git config --global user.name "。。。。"   

git config --global user.email "。。。。"   

## 常用命令

### 1.git status     查看当前仓库状态

```b
一般git管理的文件有两种状态分为未跟踪和已跟踪 

未跟踪：文件没有被git管理

已跟踪：已被管理  （又分未修改、修改和暂存——未提交到git仓库） 

```

####  git add filename

```bash
 将未跟踪文件切换到暂存状态
 add * 将所有已修改（为跟踪）的文件暂存
```

#### git commit  -m “xxxx”

```bas
 将暂存状态文件存(提交)储到仓库中 变为未修改状态
 修改——》未修改   要先暂存再提交也就是  先add 在commit 
  -m 提交信息        -a 提交所有已修改（未跟踪的不会提交）  将修改变为暂存
```

### 2.git log

```ba
查看提交记录
```

### 3.git init

```bash
初始化仓库（真实开发一般不用）
```

### 4.git restore filename

```ba
将已修改的文件恢复到上次提交的状态   也可以恢复删除的文件
git restore --staged filename  取消暂存状态 尽管是删除的文件
```

![](C:\Users\LENOVO\Desktop\练习文件\360截图20230206120143627.jpg)

>执行上述命令后

![](C:\Users\LENOVO\Desktop\练习文件\360截图20230206120149950.jpg)

### 5. git rm filename

```bash
 从系统和git仓库中同时删除  #当文件处于修改状态是无法删除   
 git rm filename -f  #强制删除 无论状态
 git rm --cached <file/file parth> #把文件从暂存区域移除,但仍保留本地  文件   当要移除的是文件夹时要使用递归移除 -r
```

### 6.git mv

```ba
移动文件  如果移动目的地和源相同则是文件重命名
```

## 分支  树形结构

![](C:\Users\LENOVO\Desktop\练习文件\360截图20230206124219791.jpg)

```ba
分支与分支之间相互独立，针对master主分支来创建新功能、bug等不同的分支，不能改动主分支
实际开发中，都是在自己的分支上编写代码，编写完毕，将自己的分支合并到主分支
```

### 图例

![](C:\Users\LENOVO\Desktop\练习文件\360截图20230206155013937.jpg)

master为已经上线的主分支，update为新功能分支，bug1位修改bug分支，当bug修改完毕要与master分支合并

```bash
git branch   #查看仓库分支
git branch  xxx  #可以创建分支
git brach -d xxx  #可以删除分支
git checkout (branchname) #切换分支老板
git switch xxx  #新版切换分支   switch -c  创建并切换
```

### 分支合并

如上图当bug1修改完毕，c4与c8处于同一条线完成快速合并，此时master处于c8位置，当update分支新功能完成后，update与master修改一个文件时会产生合并产生冲突，根据情况选择both、current、incomeing。

```bash
git merge (branchname) #将当前分支与指定branche分支合并
```

#### 变基合并

为了避免项目中反复创建、合并、删除分支的操作，简化代码提交的记录，变基的概念就是改变分支基底。 

```bash
git rebase <branchname>  #branchname为目标基底
```

##### 原理

​	1.当我们发起变基时，git会首先找到离两条分支最近的共同祖先
​	2.对比当前分支相较于祖先分支的历史提交，并且将他们提取出来存储到一个临时文件中
​	3.将当前分支指向目标基底
​	4.以当前基底开始，重新执行临时文件件中历史操作

##### 结论

变基合并相对于普通merge合并最终结果是一样的，变基使得代码提交记录更清晰简洁。

大部分情况下合并和变基时可以互换的，但当我们已经把分支提交到远程仓库时，这时尽量不要使用变基

## 远程仓库  2月7日

远程git仓库和我们本地的没有本质区别，远程仓库可以被多人同人访问，方便协同工作

向他人远程仓库推送代码之前，一定要先下载他人远程仓库最新代码

将本地仓库上传：

```bash
git remote add origin xxxxxxx  # xxx代表远程仓库的地址  origin表示远程仓库名称  将本地库与远程库关联
git branch -M main  # 修改当前分支的名字为main
git push -u origin main  #将代码上传远程仓库并与当前分支关联  main本地主分支的名称  
git push <远程库名><本地分支>:<远程分支> #将本地分支代码推送到指定远程分支
```

### 操作命令

```bash
git remote #显示当前所关联的所有远程库
git remote remove origin #删除远程仓库
git clone xxxx hello  
# xxx代表想要克隆远程仓库的地址  从远程库下载代码  hello表示创建新文件夹并将克隆的代码放入其中
git push #如果本地库的代码版本低于远程库 无法推送
git fetch #确保本地库和远程库的版本一直才可推送  fetch从远程库下载代码 但不会将下载的代码与本地当前分支自动合并
          #使用fetch下载代码后  要手动合并
git pull #从服务器下载代码并自动合并  但不能处理冲突
```





```bash
git switch <commit id> #通过log查询提交记录  利用唯一提交id将头切换到指定节点 这个操作会分离头指针 
                       #头指针指向决定当前代码显示内容  头应该指向某一个分支
```

​	·当头指针没有指向某一个分支所在节点时，这种状态称为分离头指针，这种状态下也可以操作代码，但这些操作不会出现在任何分支上，所以不要在分离头指针的状态下操作仓库。

​	·可以通过在要切换的节点上创建一个分支来解决上述问题

```bash
git switch -c xxx <commit id>  # 头切换到指定节点 并创建xxx分支
```

### tag标签

可以为提交记录设置标签，以达到快速找到该开发节点，标签没有任何特殊效果，切换节点时仍然会产生分离指针

```bash
git tag  #显示标签
git tag hello <commit id> #为此提交id打上hello标签  若不加commit id 则为当前节点添加标签
git switch hello #可以通过标签名切换节点
git push 远程仓库 标签名 #推送标签到远程仓库
git push 远程仓库 --tags #推送所有标签到远程仓库
git tag -d 标签名  #删除本地标签
git push 远程仓库 --delete 标签名/分支名 #删除远程仓库标签
```

### git ignore

​	·默认情况下，git会监视我们文件夹中所有文件，但有些文件我们不希望被git管理。可以通过在项目文件夹中添加一个.gitignore文件，来设置那些需要git忽略的文件

![](C:\Users\LENOVO\Desktop\练习文件\360截图20230207135408608.jpg)



## github静态页面

- [ ] 在github中，可以将自己的静态页面部署到github中，他给我们提供一个地址供他人访问。
- [ ] 要求静态页面分支必须为：gh-pages

















