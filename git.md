### 1.如何从github上同步项目到本地

```
1. 本地建一个文件夹：在该文件夹内，右键点击在此处打开cmd
2. git init
3. git remote add origin https://github.com/dengsiwen/spring-boot.git
4. git pull origin master
以上四步，不出意外是可以同步成功，如果中间报错，一般都是由于冲突导致，比如本地和远程存在相同的名字（README.md），又同时做了修改
```

```
问题一：git pull 失败 ,提示：fatal: refusing to merge unrelated histories
关于这个问题，可以参考http://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories。
在进行Git pull 时，添加一个可选项
git pull origin master --allow-unrelated-histories
```

### 2. 本地修改代码后，提交到远程

```
1. git add *
2. git commit -m * (*可以写中文说明)
3. git push -u origin master
```

### 3. github创建repository后，将本地项目同步至github

```
echo "# java-api" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/dengsiwen/java-api.git
git push -u origin master
```

### 4. 本地保存账号密码，不需要每次提交都输入

```
1. git config --global credential.helper store
此操作会在用户主目录：C:\Users\用户名下生成一个.gitconfig文件【C:\Users\Administrator】内容为：
[credential]
helper = store
2. 在.gitconfig文件中添加账号密码配置
[user]
    name = dengsiwen
    email = 491408802@qq.com
3. 在同级目录下创建文件：.git-credentials（由于在Window中不允许直接创建以"."开头的文件，所以需要借助git bash进行，打开git bash客户端）
   在同级目录打开git bash，用touch创建文件 
   touch .git-credentials
   输入内容保存：
   https://dengsiwen:dsw418418@github.com
```

### 5. github同步项目到gitbook

```
1. gitbook上创建一本书，setting选项进行设置：Github，选择某一个，中间可能会是一把×，可以点击右边的Github，就会变成IN SYNC
2. 为了显示目录,可以在github页面建立SUMMARY.md，内容如下
# Summary
* [1. Stream]()
  * [1.1 流到底是什么]()
1）# 和 *
2）Tab空格
3）[]和(Stream/xxx.md或者/xxx.md)
```



