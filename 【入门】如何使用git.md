# 【入门】如何使用git?

## 1.文件的提交，更改与回退

#### 前置知识

```bash
mkdir notes # 创建一个名为notes的文件夹
cd notes # 进入notes文件夹
touch note.html note.css # 创建两个文件
ls # 查看当前文件夹中的文件
rm note.css # 删除文件 
clear # 清屏
```

#### 提交

```bash
git init # 初始化
git add note.html # 提交note.html文件
git add . # 提交当前文件夹的所有文件
git commit -m 'add note.html and note.css' # 写提交注释
```

####  更改文件


```bash
rm note.html # 删除文件
touch note.js # 创建一个新文件
git add . # 提交
git commit -m 'delete note.html and add note.js' # 写注释
```

#### 查看日志

```bash
git log # 查看日志

# 会出现类似以下的信息
commit eee754494ad59923b5b43eeef791e7774372cda7 (origin/master, master)
Author: Neco <NeCo@oyj.com>
Date:   Tue May 12 20:13:26 2026 +0800

    delete html and add app.js

commit 39c75c1d0b78c91929464cf3ce3625b6b5a602df
Author: Neco <NeCo@oyj.com>
Date:   Tue May 12 20:08:43 2026 +0800

    add a html and css file
```

#### 回退

```bash
# 复制日志中的commit的哈希码
git checkout 39c75c1d0b78c91929464cf3ce3625b6b5a602df
# 这样我们就能回退到之前的状态
# 并且处于一个新的分支(branch)中
```

#### 切换分支

```bash
git branch # 查看当前所有分支
git checkout master # 切换回master分支
```

#### 创建新分支

```bash
git checkout -b new-branch # 创建新分支
```

## 2. github仓库中 **推送** 与 **拉取** 文件

#### 前置操作

​	在github创建一个仓库 ，建完之后会出现以下界面：

​	![](C:\Users\20505\Pictures\Screenshots\屏幕截图 2026-05-12 220759.png)

#### 推送

```bash
# 绑定到这个仓库
git remote add origin https://github.com/SuddenRain-37/learing_note.git 
# 推送代码
git push -u origin master
```

​	文件就成功推送了

![](C:\Users\20505\Pictures\Screenshots\屏幕截图 2026-05-12 221616.png)

#### 什么时候要拉取？

​	先模拟一下什么时候会拉取文件(通常是别人推送的新分支，你合并到了你的github仓库中，你需要更新本地文件时)

```bash
git checkout -b new-branch # 创建新分支
touch note.py # 在分支中创建新文件
git add . # 提交所有文件
git commit -m 'add a py flie' # 写注释
git push origin new-branch # 推送新分支
```

​	这样，你的github仓库就会多出一个分支：

![](C:\Users\20505\Pictures\Screenshots\屏幕截图 2026-05-12 223623.png)

​	在同意合并请求后：

![](C:\Users\20505\Pictures\Screenshots\屏幕截图 2026-05-12 223727.png)

​	你的github仓库中就会有新分支的文件

![](C:\Users\20505\Pictures\Screenshots\屏幕截图 2026-05-12 223948.png)

#### 拉取

```bash
git pull origin # 拉取github仓库中的代码
```





