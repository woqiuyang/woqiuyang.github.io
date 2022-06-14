---
title: EasyExcel
date: 2020-5-25 00:50:54
cover: https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220525005115.png
tags:
- 组件
---

# Apache POI
> 有SAX模式和Dom模式解析，
Dom是一次性读取，容易造成内存溢出
SAX模式相对比较复杂，在Excel03和07版本，数据存储的方式截然不同，sax解析方式也不同
> 一个3M的Excel依然需要100M的内存

## userModel模式
> 大部分使用POI都是使用userModel模式，随便拷贝个代码就能用，但是转换要几百行代码，
而且十分消耗内存，在并发情况下，会造成OOM和频繁的full gc

# EasyExcel的改进
## 重写了POI对07版本的Excel解析
> 把内存消耗从100m降到了10m左右，并且再大的Excel也不会出现内存溢出，但是03版依然依赖于SAX模式