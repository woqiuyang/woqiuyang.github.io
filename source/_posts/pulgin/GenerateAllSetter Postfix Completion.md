---
title: GenerateAllSetter Postfix Completion
date: 2022-6-20 20:13:43
cover: 
tags:
- 插件
---
生成 set
```java
foo.allset
```
根据一段含有源对象（a）/目标对象（b）的 b.setXxx(a.getXxx()) 方法代码生成所有 set 方法以快速实现对象转换
```java
public void usage05() {
    // 用法5, 将 src 的数据赋值给 dest, 常用于两个不同类直接进行 convert(需字段名称相同), 通过 postfix
    Foo src = new Foo();
    Foo dest = new Foo();
    // 取消下面的注释, 光标位于 convert 后面, 按下 Tab 键
//        dest.setTestInt(src.getTestInt());.convert
    // 即可得到下面结果
    dest.setTestInt(src.getTestInt());
    dest.setTestLong(src.getTestLong());
    dest.setTestFloat(src.getTestFloat());
    dest.setTestDouble(src.getTestDouble());
    dest.setTestBoolean(src.getTestBoolean());
}
```
