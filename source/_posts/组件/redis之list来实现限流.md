---
title: redis之list来实现限流
date: 2022-5-30 11:50:07
cover: 
tags:
- 组件
---
```java
		String key = "userId" + "接口名" ;
        int listLength = llen(key);
        if (listLength < 10) {
        lpush(key, new ());
        } else {
        long time = lindex(key, -1);
        if (now() - time < 60) {
        System.out.println("访问频率超过了限制，请稍后再试");
        } else {
        lpush(key, now);
        ltrim(key, 0, 9);
        }
        }

```
![](![](https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220530115137.png))