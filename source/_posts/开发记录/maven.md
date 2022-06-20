---
title: maven
date: 2022-6-10 10:34:00
cover: 
tags:
- 开发记录
---
# 命令行跳过测试打包
```shell
mvn clean install -Dmaven.test.skip=true
```

# 明明有本地文件，idea却找不到包
在idea中使用maven时常常出现配置好pom依赖后，怎么reimport都无法下载jar包。
解决方法：在Maven窗口中打开mvn命令，输入更新不完整依赖命令：
```shell
mvn -U idea:idea
```
运行，就可以下载没有的jar包。

# maven红色波浪线
通过上面的命令jar包已经导入了成功也不能消除（reimport也不行，不过可以正常使用），可以先将带红色波浪线的依赖剪切掉，reimport一下，再将依赖粘贴回去，完美解决。


# maven查找网站
https://mvn.coderead.cn/
