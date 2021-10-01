---
title: day02课后练习
tags:
  - Java
  - 课后练习
categories: Java
---


# 基础题目:

## 第一题

* 按步骤编写代码，效果如图所示：

![](img\1.jpg)

* 编写步骤：

1. 定义类 Test1

2. 定义 main方法

3. 定义两个byte类型变量b1,b2,并分别赋值为10和20.

4. 定义变量b3,保存b1和b2的和,并输出.

5. 定义两个short类型变量s1,s2,并分别赋值为1000和2000.

6. 定义变量s3,保存s1和s2的和,并输出.

7. 定义一个char类型变量ch1赋值为'a',一个int类型变量i1赋值为30.

8. 定义变量ch3,保存c1和i1的差,并输出.

## 第二题

* 按步骤编写代码，效果如图所示：

  ![](img\2.jpg)



* 编写步骤：

  1. 定义类 Test2
  2. 定义 main方法
  3. 定义 int类型变量i1 和 long类型变量l1
  4. 定义变量add,保存i1和l1的和,并输出.
  5. 定义 long类型变量l2 和 float类型变量f2
  6. 定义变量add2,保存l2和f2的和,并输出.
  7. 定义 int类型变量i3 和 double类型变量d3
  8. 定义变量add3,保存i3和d3的和,并输出.
  9. 定义 float类型变量f4 和 double类型变量d4
  10. 定义变量add4,保存f4和d4的和,并输出.

## 第三题

- 按步骤编写代码，效果如图所示：

  ![](img\3.jpg)

- 编写步骤：

  1. 定义类 Test3
  2. 定义 main方法
  3. 定义char类型变量ch,赋值为'J'
  4. 使用强制转换的方式,将变量ch转换为小写'j',并输出
  5. 定义char类型变量ch2,赋值为'a'
  6. 使用+=的方式,将变量ch2转换为大写'A',并输出
  7. 定义double类型变量d3,int类型变量i3
  8. 定义double变量sum3,保存d3与i3的和,输出sum3的值和sum3去除小数部分的值
  9. 定义double类型变量d4,int类型变量i4
  10. 定义int变量mul4,保存d4和i4乘积的整数部分,并输出



## 第四题

- 按步骤编写代码，效果如图所示：

  ![](img\4.jpg)

- 编写步骤：

  1. 定义类 Test4
  2. 定义 main方法
  3. 定义两个int类型变量a1和a2,分别赋值10,11,判断变量是否为偶数,拼接输出结果
  4. 定义两个int类型变量a3和a4,分别赋值12,13,判断变量是否为奇数,拼接输出结果



## 第五题

- 按步骤编写代码，效果如图所示：

  ![](img\5.jpg)



* 编写步骤：
  1. 定义类 Test5
  2. 定义 main方法
  3. 定义一个int类型变量a,变量b,都赋值为20.
  4. 定义boolean类型变量bo , 判断++a 是否被3整除,并且a++ 是否被7整除,将结果赋值给bo
  5. 输出a的值,bo的值.
  6. 定义boolean类型变量bo2 , 判断b++ 是否被3整除,并且++b 是否被7整除,将结果赋值给bo2
  7. 输出b的值,bo2的值.



## 第六题

案例：为抵抗洪水，战士连续作战89小时，编程计算共多少天零多少小时？

- 按步骤编写代码，效果如图所示：

  ![1557879127503](img/6.png)


* 编写步骤：
  1. 定义类Test6
  2. 定义main方法
  3. 定义一个int类型变量hours，赋值为89
  4. 定义一个int类型变量day，用来保存89小时中天数的结果
  5. 定义一个int类型变量hour，用来保存89小时中不够一天的剩余小时数的结果
  6. 输出结果



## 第七题

案例：今天是周2，100天以后是周几？

* 按步骤编写代码，效果如图所示：

![1557879464870](img/7.png)

* 编写步骤：
  1. 定义类Test7
  2. 定义main方法
  3. 定义一个int类型变量week，赋值为2
  4. 修改week的值，在原值基础上加上100
  5. 因为week的值加上100后超过了星期的范围，重写修改week的值
  6. 输出结果，在输出结果的时候考虑特殊值，例如周日



## 第八题

案例：求三个整数x,y,z中的最大值

* 按步骤编写代码，效果如图所示：

![1557879847378](img/8.png)

* 编写步骤：

  1. 定义类Test8
  2. 定义main方法
  3. 定义三个int类型变量,x,y,z，随意赋值整数值
  4. 定义一个int类型变量max，先存储x与y中的最大值（使用三元运算符）
  5. 再次对max赋值，让它等于上面max与z中的最大值（使用三元运算符）
  6. 输出结果



## 第九题

案例：给定一个年份，判断是否是闰年

闰年的判断标准是：

​       1）可以被4整除，但不可被100整除

​       2）可以被400整除

* 按步骤编写代码，效果如图所示：

![1557902649882](img/9.png)

* 编写步骤：
  1. 定义类Test9
  2. 定义main方法
  3. 定义一个int类型变量year，随意赋值一个年份
  4. 定一个一个boolean类型变量，用来保存这个年份是否是闰年的结果
  5. 输出结果



## 第十题

案例：小明要到美国旅游，可是那里的温度是以华氏度为单位记录的。它需要一个程序将华氏温度（80度）转换为摄氏度，并以华氏度和摄氏度为单位分别显示该温度。

![1557903785834](img/1557903785834.png)

* 按步骤编写代码，效果如图所示：

  ![1557903814057](img/1557903814057.png)

* 编写步骤：
  1. 定义类Test10
  2. 定义main方法
  3. 定义一个double类型变量hua，存储华氏温度80
  4. 定义一个double类型变量she，存储摄氏温度，根据公式求值
  5. 输出结果



# 阅读代码题：

## 第一题

```java
如下代码的计算结果是：
int i = 1;
i *= 0.2;  
i++;
System.out.println("i=" + i);
```

## 第二题

```java
如下代码的运算结果是：
int i = 2;
i *= i++;

int j = 2;
j *= j+1; 

int k = 2;
k *= ++k;

System.out.println("i=" + i);
System.out.println("j=" + j);
System.out.println("k=" + k);
```

## 第三题

```java
	public static void main(String[] args) {
		int a = 3;
		int b = 1;
		if(a = b){
			System.out.println("Equal");
		}else{
			System.out.println("Not Equal");
		}
	}
```


## 第四题

```java
	public static void main(String[] args) {
		int a = 8, b = 3;
		System.out.println(a>>>b);
		System.out.println(a>>>b | 2);
	}
```

```java

public class Test1 {
    public static void main(String[] args) {
        /**
         * 第一题
         */
//        Byte b1 =10;
//        Byte b2 = 20;
//        int b3 = b1 + b2;
//        System.out.println("b3 = " + b3);
//        short s1 = 1000;
//        short s2 = 2000;
//        int s3 = s1+s2;
//        System.out.println("s3 = " + s3);
//        char ch1='a';
//        int i1=30;
//        int ch3 = ch1-i1;
//        System.out.println("ch3 = " + ch3);
        /**
         * 第二题
         */
//        int i1 =0;
//        long l1 = 0;
//        long add = i1 + l1;
//        System.out.println("add = " + add);
//
//        long l2 = 1;
//        float f2 = 2.0f;
//        float add2 = l2 + f2;
//        System.out.println("add2 = " + add2);
//
//        int i3 = 3;
//        double d3 = 5.1345;
//        double add3 = i3 + d3;
//        System.out.println("add3 = " + add3);
//
//        float f4 = 3.14f;
//        double d4 = 3.1415926;
//        double add4 = f4 + d4;
//        System.out.println("add4 = " + add4);
        /**
         * 第三题
         */
//        char ch = 'J';
//          ch = (char) (ch + 32);
////        char ch1 = (char)(ch +32);
//        System.out.println("ch = " + ch);
//
//        char ch2 = 'a';
//        ch +=32;
//        System.out.println("ch2 = " + ch2);
//
//        double d3= 20.1;
//        int i3 = 555;
//        double sum3 = d3 + i3;
//        System.out.println("sum3 = " + sum3);
//        int sum4= (int)sum3;
//        System.out.println("sum4 = " + sum4);
//
//        double d4 = 5.555;
//        int i4 = 4396;
//        int mul4 = (int) (d4 * i4);
//        System.out.println("mul4 = " + mul4);

//        /**
//         * 第四题
//         */
//        int a1 = 10,a2 = 11;
//        String s1 =  a1%2 == 0 ? "偶数" : "奇数";
//        System.out.println("10是否是偶数: 是" + s1);
//        String s2 =  a2%2 == 0 ? "偶数" : "奇数";
//        System.out.println("11是" +s2);
//        int a3 = 12,a4 = 13;
//        System.out.println("12是" + (a3 % 2 == 0));
//        System.out.println("13是" + (a4 % 2 == 0));

        /**
         * 第五题
         */
//        int a = 20,b = 20;
//        boolean bo = false;
//        if (++a % 3 == 0 && a++ % 7 ==0){
//            bo = true;
//            System.out.println("a = " + a);
//        }else{
//            System.out.println("bo == " + false);
//            System.out.println(a);
//        }
//        boolean bo2 = false;
//        if (b++ % 3 == 0 && ++b % 7 == 0){
//            bo2 = true;
//            System.out.println("b = " + b);
//        }else {
//            System.out.println(bo2);
//            System.out.println("b = " + b);
//        }


//        boolean bo3 = ((++a % 3) == 0 && (a++ % 7 == 0));
//        boolean bo4 = ((b++ % 3 ) == 0 && (++b % 7 == 0));
//        System.out.println("bo3 = " + bo3);
//        System.out.println("bo4 = " + bo4);
//        System.out.println("a = " + a);
//        System.out.println("b = " + b);

        /**
         * 第六题
         */
//        int hours = 89;
//        int day = hours / 24;
//        int hour= hours % 24;
//        System.out.println("战士连续作战" + day +"天"+hour+"小时");
        /**
         * 第七题
         */
//        int week = 2;
//        week += 100;
//        week = week % 7;
//        System.out.println("week = " + week);

        /**
         * 第八题
         */
//        int x=1,y=2,z=3;
//        int max = x>y ? x : y;
//        System.out.println("max = " + max);
//        max = max > y ? max : z;
//        System.out.println("max = " + max);
        /**
         * 第九题
         */
//        int year = 2000;
//        boolean bl=((year % 4 ==0 && year % 100 != 0) || (year % 400 == 0));
//        System.out.println("bl = " + bl);
        /**
         * 第十题
         */
//        double hua = 80;
//        double she = (hua-32)/1.8;
//        System.out.println("she = " + she);

        /**
         * 阅读代码题
         */
//        int i = 2;
//        i *= i++;
//        int j = 2;
//        j *= j+1;
//        int k = 2;
//        k *= ++k;
//        System.out.println("i=" + i);
//        System.out.println("j=" + j);
//        System.out.println("k=" + k);
//        4 4 6



//        int i = 1;
//        i *= 0.2;
//        i++;
//        System.out.println("i=" + i);

//        1

//        int a = 3;
//        int b = 1;
//        if(a = b){  //编译错误
//            System.out.println("Equal");
//        }else{
//            System.out.println("Not Equal");
//        }

//            int a = 8, b = 3;
//            System.out.println(a>>>b); //1
//            System.out.println(a>>>b | 2); //3

    }
}

```

