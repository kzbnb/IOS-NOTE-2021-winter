# 2021寒假——IOS开发笔记

## 1. Object-C介绍

### 1.简介

1. 是C的超集，C/C++/OC都是Clang编译，可以混编
2. 基本类型
   * 其他语言基本相同
   * 32位取前者，64位取后者
     1. Interger(int/long) 
     2. CGFloat(float/double) 
   * BOOL类型值为(YES/NO)

### 2. Foundation

###### 	将基本类型封装成对象，也可将对象返回基本类型。

##### 	@用于包装

##### 	1. NSNumber：数字，各种格式的数字

```objective-c
NSNumber *four=@4;
```

> https://developer.apple.com/documentation/foundation/nsnumber?changes=latest_major&language=objc

#####     2.NSString：字符串

```objective-c
NSString * string = @"字符串";
```

##### 	3.NSData：二进制

##### 	4.NSDate：时间

##### 	5.NSArray：数组

​	类似于ArrayList。

```objective-c
NSArray *array=@[@1,@2,@3];
```

 + 注意nil：为0，常会作为异常处理。

 + 注意*mutable*可变，*immutable*不可变，在OC明显区分。

 ##### 6. NSDictionary

   - 类似于hashmap

   - 注意nil

     思考：NSString、Array、Dictionary的属性copy集合的深浅拷贝

### 3.Define Class

- Interface:类定义从@interface开始，它表示了类的接口声明.**基本所有对象继承自NSObject**.

- Property:

  > 简单点说，属性（变量）就是一种支持访问对象成员变更的快捷的方法，可以自动的生成setter和getter方法.其中()内为修饰符：默认nonatomic&后接各种属性.

  >https://blog.csdn.net/dfqin/article/details/11669993

- 方法没有访问权限的限定符。能否被访问取决于头文件中有无暴露这个方法。

- 方法一般有两种。

  1. 成员方法 -
  2. 类方法（static的方法）+
  
- 入参形式不同。

  ```objc
  单函数参数的情况下:
  -(void)call:(int *)array;
  对应的C++函数应该是这么写:
  void call(int *array);
  
  多函数参数的oc方法
  需要声明参数的别称
  -(void)call:(int *)array array_size:(int)size;
  对应的C++函数:
  void call(int *array, int size);
  而调用oc方法call时  应该指定参数名为array_size而不是size
  int array[] = {1,2,3};
  Body *body = [Body alloc];
  [body call:array array_size:3];
  ```

> https://blog.csdn.net/qq_21358401/article/details/79573938



- selector:

  > @selector(xxxx)的作用是找到名字为xxxx的方法。一般用于[a performSelector:@selector(b)];就是说去调用a对象的b方法，和[a b];的意思一样，但是这样更加动态一些。   
>
  > https://www.cnblogs.com/geek6/p/4106199.html

- Category:增强类功能（如增强标准库、提供安全方法）、分离类实现（辅助性的工作） 在其中使用property是不生成成员变量的
  
- Extension：主要增加成员变量、用于接口分离，可起到Private的作用(readonly)
  
- Category VS Extension？
  
   
  
   

