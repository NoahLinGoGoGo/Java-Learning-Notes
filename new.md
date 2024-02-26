[TOC]

# 核心实践派

##  数组
```java
import java.util.List; 
/*
List：一种有序列表的集合的接口，例如，按索引排列的Student对象的List；
java.util.Set：一种保证没有重复元素的集合的接口，例如，所有无重复名称的Student对象的Set；
*/
import java.util.ArrayList;
import java.util.Collections;

List<String> hotWords = new ArrayList<>();

hotWords.add("carrot");
hotWords.add("tomato");
hotWords.add("patato");
/*
遍历数组
方式1：使用标准的for循环
方式2：for each
方式2：Arrays.toString(array)打印,适用long，float，double，int，boolean，byte，object元素的一维数组，
对于引用类型的数组，需要重写该引用Object的 toString() 方法
*/
for (int i = 0; i < hotWords.size(); i ++) {
    String value = hotWords.get(i);
    System.out.println(value); // carrot\n tomato\n patato\n
}
/*
数组排序
1.对于String或Integer这些已经实现Comparable接口的类来说，可以直接使用Collections.sort方法传入list参数来实现默认方式（正序）排序；
2.如果不想使用默认方式（正序）排序，可以通过Collections.sort传入第二个参数类型为Comparator来自定义排序规则；
        Collections.sort(intList,new Comparator<Integer>() {
            @Override
            public int compare(Integer o1, Integer o2) {
                // 返回值为int类型，大于0表示正序，小于0表示逆序
                return o2-o1;
            }
        });
*/
Collections.sort(hotWords);
for (String value : hotWords) {
    System.out.println(value);  // carrot\n  patato\n tomato\n
}
//hotWords.addAll(list2);
//hotWords.remove(0);
//hotWords.clear();

// 上面的hotWords准确的叫法是集合，下面两个定义才是真正的数组，不过下面的相比在开发中用得少
char[] helloArray = { 'h', 'e', 'l', 'l', 'o'}; // 注意是 小括号
int[] pixels = new int[256]; // 固定大小数组，长度256
helloArray = null;

```
##  字符串, Java中String是个对象
```java
import java.lang.String;

String keyword = mInputBox.getText().toString().trim(); // trim() 方法用于删除字符串的开头和结尾的空白字符

String packageName = "com.ximalaya.guangzhou";
System.out.println(packageName.length());  // 22
System.out.println(packageName.charAt(3));  // . index从0开始
System.out.println(packageName.equals("com.ximalaya.guangzhou")); //true
System.out.println(packageName.endsWith("com")); // false
System.out.println(packageName.startsWith("com")); // true
System.out.println(packageName.replace("guangzhou","shenzhen")); //com.ximalaya.shenzhen
System.out.println(packageName.toLowerCase()); //com.ximalaya.guangzhou
System.out.println(packageName.toUpperCase()); //COM.XIMALAYA.GUANGZHOU
System.out.println(packageName.contains("ximalaya")); //true
System.out.println(packageName.isEmpty()); // false
System.out.println(packageName.substring(3)); // .ximalaya.guangzhou, 包含 fromindex
// 等等API
```
##  Map

`Map`这种键值（key-value）映射表的数据结构，作用就是能高效通过`key`快速查找`value`（元素）。和`List`类似，`Map`也是一个接口，最常用的实现类是`HashMap`

```java
import java.util.HashMap;
import java.util.Map;

Map<String,String> map = new HashMap<>();

map.put("username","John"); 
map.put("password","123456"); 

System.out.println(map.get("username"));  // John
System.out.println(map.containsKey("password")); // true

//遍历enumerate KEY, 注意不保证顺序
for (String key : map.keySet()) {
    System.out.println(key); 
}

//遍历enumerate KEY和VALUE, 注意不保证顺序
//for (Map.Entry<String, Integer> entry : map.entrySet()) {
    //String key = entry.getKey();
    //Integer value = entry.getValue();
    //System.out.println(key + " = " + value);
//}

```
##  类和对象
```java
package com.example.sdklibrary.tools;

import com.google.gson.Gson;
import com.google.gson.JsonNull;
import com.google.gson.JsonSyntaxException;
import com.google.gson.reflect.TypeToken;

import org.json.JSONObject;

import java.lang.reflect.Type;
import java.util.Map;

/**
 * Gson工具类，本来这个类中还有很多个方法，例如gson转为map,object等等由于和这个知识点相同，没有好讲解的，我删除了  
 */

public class GsonUtils {

    private static Gson gson = null;
     /**
     静态块: 用static{}裹起来的代码片段，只会被执行一次，第一次加载此类时执行，静态块 先于 构造块执行。
     static{
     //code
     }

     构造块: 用{}裹起来的代码片段，构造块在创建对象时会被调用，
     每次创建对象时都会被调用，并且优先于类构造函数执行。构造块中定义的变量是局部变量。
     {
     //code
     }

    其实下面的 静态块 也可以写成 单例，这里不用单例是因为没必要，类的方法都是static的
    private static GsonUtils getInstance() {
        if (gson == null) {
            gson = new Gson();
        }
        return netRequest;
    }
     */
    static {
        if (gson == null) {
            gson = new Gson();
        }
    }
    /**
    构造函数constructor
    可以定义多个构造方法，编译器根据参数自动判断。
    可以在一个构造方法内部调用另一个构造方法，便于代码复用。
    */ 
    private GsonUtils() {
    }

    /**
     * 将json转成bean
       java中有很多<T>这种写法，是 泛型 ，注意类型参数只能代表引用型类型，不能是基本类型
    */
    public static <T> T GsonToBean(String gsonString, Class<T> cls) {
        T t = null;
        if (gson != null) {
            t = gson.fromJson(gsonString, cls);
        }
        return t;
    }
}

## 泛型

在看项目代码时候我经常遇到 泛型 语法，和iOS 不一样

// 泛型方法 printArray                         
public static <E> void printArray( E[] inputArray ) {
      // 输出数组元素            
         for ( E element : inputArray ){        
            System.out.printf( "%s ", element );
         }
         System.out.println();
}

// 限制参数的类型"extends"（类）或者"implements"（接口），泛型方法，比较三个值并返回最大值
public static <T extends Comparable<T>> T maximum(T x, T y, T z) {                     
      T max = x; // 假设x是初始最大值
      if ( y.compareTo( max ) > 0 ){
         max = y; //y 更大
      }
      if ( z.compareTo( max ) > 0 ){
         max = z; // 现在 z 更大           
      }
      return max; // 返回最大对象
}

// 泛型类
public class Box<T> {
   
  private T t;
 
  public void add(T t) {
    this.t = t;
  }
 
  public T get() {
    return t;
  }
 
  public static void main(String[] args) {
    Box<Integer> integerBox = new Box<Integer>();
    Box<String> stringBox = new Box<String>();
 
    integerBox.add(new Integer(10));
    stringBox.add(new String("菜鸟教程"));
 
    System.out.printf("整型值为 :%d\n\n", integerBox.get());
    System.out.printf("字符串为 :%s\n", stringBox.get());
  }
}

// 类型通配符 ?, 例如 List<?> 在逻辑上是 List<String>,List<Integer> 等所有 List<具体类型实参> 的父类。
public static void getData(List<?> data) {
      System.out.println("data :" + data.get(0));
}
   
public static void getUperNumber(List<? extends Number> data) {
          System.out.println("data :" + data.get(0));
}
```

## 基类Object和常用函数

Object 类位于 java.lang 包中, 是所有类的父类。哪怕在Java中定义隐式继承`public class UserBean {}`，其实等价于`public class UserBean extends Object{}`。

[Object类的API](https://www.runoob.com/java/java-object-class.html)


