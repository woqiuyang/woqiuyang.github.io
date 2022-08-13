---
title: FastJson
date: 2020-5-20 23:28:06
cover: https://blog-1258707945.cos.ap-guangzhou.myqcloud.com//blog/20220523232857.png
tags:
- note
---
# 什么是json
**json是数据交换语言**
# Json数据格式
两种数据格式，对象与数组(List集合和Map集合不同)
# TypeReference
转换Map的过程中，不能设置泛型，没有泛型是不安全的，使用TypeReference，传入转后的Map集合
结尾加上{},传入空的匿名内部类，因为TypeReference是protected修饰的构造方法，匿名内部类就是子类的内部对象
```java
Map<String,Student> map = JSON.parseObject(jsonString,new TypeReference<Map<String,Student>>(){});
```
# SerializerFeature 
进行序列化时，定制自己的需求的枚举

## 设置空值为null
fastJson序列化的时候，空值是不会序列化的
```java
 Student student = new Student();
        student.setId("1");
        student.setName("张三");
        student.setAge(null);
        // 将student对象转换成Json字符串
        String s = JSON.toJSONString(student, SerializerFeature.WriteMapNullValue);
        System.out.println(s);
```
输出
```json
{"age":null,"id":"1","name":"张三"}
```
## 设置空字段为双引
```java
        String s = JSON.toJSONString(student, SerializerFeature.WriteNullStringAsEmpty);
```
```json
{"age":"","id":"1","name":"张三"}
```
## 设置空布尔为false
```java
        student.setIsStudent(null);
        String s = JSON.toJSONString(student, SerializerFeature.WriteNullBooleanAsFalse);

```
```json
{"age":null,"id":"1","isStudent":false,"name":"张三"}
```

## 格式化日期
```java
student.setBirthday(new Date());
String s = JSON.toJSONString(student, SerializerFeature.WriteNullBooleanAsFalse);
```
```json
{"age":null,"birthday":1653325416158,"id":"1","isStudent":false,"name":"张三"}
```
添加格式化
```java
        String s = JSON.toJSONString(student, SerializerFeature.WriteNullBooleanAsFalse,SerializerFeature.WriteDateUseDateFormat);
        System.out.println(s);
```

```json
{"age":null,"birthday":"2022-05-24 01:06:39","id":"1","isStudent":false,"name":"张三"}
```

## 格式化输出
```java
String s = JSON.toJSONString(student, SerializerFeature.PrettyFormat,SerializerFeature.WriteDateUseDateFormat);
        System.out.println(s);
```
```json
{
	"birthday":"2022-05-24 01:13:18",
	"id":"1",
	"name":"张三"
}
```

# JSONField
## name
```java
    // name 指定序列化后的名字，
@JSONField(name = "studentName")
private String name;
```
```json
{
	"birthday":"2022-05-24 01:16:59",
	"id":"1",
	"studentName":"张三"
}
```
## ordinal
```java
    // 指定序列化后的顺序，值越小，越靠前
    @JSONField(ordinal = 2)
    private String age;
```
## format
```java
    @JSONField(format = "YYYY-MM-dd")
    private Date birthday;
```
```json
{
	"birthday":"2022-22-24",
	"id":"1",
	"name":"张三"
}
```
## serialize
该字段是否被序列化，默认true
```java
    @JSONField(serialize = false)
    private String name;
```
```json
{
	"birthday":"2022-05-24",
	"id":"1"
}
```
## deserialize
**在参与反序列化的过程中，这个字段不参与成为对象的一部分**
```java
    @JSONField(deserialize = false)
    private String age;
```






