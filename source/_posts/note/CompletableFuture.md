---
title: CompletableFuture常用记录
date: 2020-5-27 00:52:44
cover: https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220527005307.png
tags:
- note
---

# 工具类
```java
public class SmallTool {

    public static void  sleepMillis(Integer millis){
        try {
            Thread.sleep(millis);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }

    public static void printTimeAndThread(String  tag){
        String result = new StringJoiner("\t|\t")
                .add(String.valueOf(System.currentTimeMillis()))
                .add(String.valueOf(Thread.currentThread().getId()))
                .add(Thread.currentThread().getName())
                .add(tag)
                .toString();
        System.out.println(result);
    }
}

```
# 例子一
```java
    public static void main(String[] args) {
        SmallTool.printTimeAndThread("我进了饭堂");
        SmallTool.printTimeAndThread("我点了滑鸡饭");
        // supplyAsync是java的函数式编程接口，叫提供者者，
        // 没有入参，只有一个返回值,因为我们返回了字符串，所以CompletableFuture的泛型是String
        CompletableFuture<String> stringCompletableFuture = CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("厨师炒菜");
            SmallTool.sleepMillis(200);
            SmallTool.printTimeAndThread("厨师打饭");
            SmallTool.sleepMillis(100);
            return "滑鸡 + 饭 好了";
        });
        SmallTool.printTimeAndThread("我在打王者");
        // join等待任务执行结束，返回任务结果
        SmallTool.printTimeAndThread(String.format("%s,小白开吃",stringCompletableFuture.join()));
    }

```
输出结果
![](https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220527011927.png)
# 例子二
一般来说，打饭这件事情是服务员干的
```java

    public static void main(String[] args) {
        SmallTool.printTimeAndThread("我进了饭堂");
        SmallTool.printTimeAndThread("我点了滑鸡饭");
        // supplyAsync是java的函数式编程接口，叫提供者者，
        // 没有入参，只有一个返回值,因为我们返回了字符串，所以CompletableFuture的泛型是String
        CompletableFuture<String> stringCompletableFuture = CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("厨师炒菜");
            SmallTool.sleepMillis(200);
            return "滑鸡";
            // thenCompose要求我们传入一个Function接口，传入参数T，经过转换后返回R
            // 将前面任务的结果返回给下一个任务
        }).thenCompose(s -> CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("服务员打饭");
            SmallTool.sleepMillis(100);
            return s+"米饭";
        }));
        SmallTool.printTimeAndThread("我在打王者");
        // join等待任务执行结束，返回任务结果
        SmallTool.printTimeAndThread(String.format("%s,小白开吃",stringCompletableFuture.join()));
    }
```
![](https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220527012705.png)
# 例子三
服务员还没做饭，要求厨师炒菜的时候，服务员同时蒸饭,要求炒菜和蒸饭同时返回，才能执行炒菜
```java
    public static void main(String[] args) {
        SmallTool.printTimeAndThread("我进了饭堂");
        SmallTool.printTimeAndThread("我点了滑鸡饭");
        // supplyAsync是java的函数式编程接口，叫提供者者，
        // 没有入参，只有一个返回值,因为我们返回了字符串，所以CompletableFuture的泛型是String
        CompletableFuture<String> stringCompletableFuture = CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("厨师炒菜");
            SmallTool.sleepMillis(200);
            return "滑鸡";
        }).thenCombine(CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("服务员蒸饭");
            SmallTool.sleepMillis(300);
            return "米饭";
        }),(s, s2) -> {
            SmallTool.printTimeAndThread("服务员打饭");
            SmallTool.sleepMillis(100);
            return String.format("%s+%s 好了",s,s2);
        });
        SmallTool.printTimeAndThread("我在打王者");
        // join等待任务执行结束，返回任务结果
        SmallTool.printTimeAndThread(String.format("%s,小白开吃",stringCompletableFuture.join()));
    }
}
```
# 三个例子的基本模型
![](https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220527013220.png)

# 例子四
**我吃完了，准备结账，要求开发票，服务员收款后，要求另一个人开发票，开发票的同时，接到电话，拿到发票，回家养猪**
使用thenCompose也能执行
```java
    public static void main(String[] args) {
        SmallTool.printTimeAndThread("我吃完了");
        SmallTool.printTimeAndThread("结账，并且要求开发票");

        CompletableFuture<String> stringCompletableFuture = CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("服务员收款 500元");
            SmallTool.sleepMillis(100);
            return "500";
        }).thenApplyAsync(s -> {
            SmallTool.printTimeAndThread(String.format("服务员开发票中 面额 %s元", s));
            SmallTool.sleepMillis(200);
            return String.format("%s元发票", s);
        });
        SmallTool.printTimeAndThread("我接到电话");
        SmallTool.printTimeAndThread(String.format("我拿到%s,准备回家",stringCompletableFuture.join()));
    }

```
# 例子五
我等车，等100路或200路公交都能到家，谁先来上谁
```java
    public static void main(String[] args) {
        SmallTool.printTimeAndThread("来到公交站");
        SmallTool.printTimeAndThread("等待100或200路公交");

        CompletableFuture<String> stringCompletableFuture = CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("等待100路公交车");
            SmallTool.sleepMillis(100);
            return "100路来了";
        }).applyToEither(CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("等待200路公交");
            SmallTool.sleepMillis(200);
            return "200路来了";
        }),s -> s);
        SmallTool.printTimeAndThread(String.format("%s,我上车了",stringCompletableFuture.join()));
    }
```
![](https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220527015316.png)
# 例子六
**我坐在车上,司机撞树上了，只能打车回家了**
```java
    public static void main(String[] args) {
        SmallTool.printTimeAndThread("来到公交站");
        SmallTool.printTimeAndThread("等待100或200路公交");

        CompletableFuture<String> stringCompletableFuture = CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("等待100路公交车");
            SmallTool.sleepMillis(100);
            return "100路来了";
        }).applyToEither(CompletableFuture.supplyAsync(() -> {
            SmallTool.printTimeAndThread("等待200路公交");
            SmallTool.sleepMillis(200);
            return "200路来了";
        }),s -> {
            SmallTool.printTimeAndThread(s);
            if (s.startsWith("100")){
                throw new RuntimeException("撞树上了");
            }
            return s;
        }).exceptionally(throwable -> {
            SmallTool.printTimeAndThread(throwable.getMessage());
            SmallTool.printTimeAndThread("打出租车回家");
            return "出租车到了";
        });
        SmallTool.printTimeAndThread(String.format("%s,我上车了",stringCompletableFuture.join()));
    }

```
# 例子七
**如果100路没来之前，就撞树上了，那么应该坐上200路公交**
