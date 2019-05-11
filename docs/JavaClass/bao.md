
```java
	package Object;

//import java.util.*;  意思是导入util下面所有的文件

import java.text.DateFormat;
import java.util.Date;

// 引用了其他包下面的类 
import Grammar.array;

public class Bao {
	
	//--------------------------------包-------------------------------------------------
	
	/*概念: 为了组织代码的方便，可以将相似的类放到一个文件夹内，这个文件夹就叫包。
	 * 
	 *用途：包不但可以包含类，还可以包含接口和其他的包。
	 *     
	 *表示：目录以"\"来表示层级关系，例如 E:\java\workspace\demo\helloWorld.java
	 *     用"."来表示层级关系，例如p1.p2.test 表示的目录为 \p1\p2\test.class
	 * */
	
	// 包的调用
	 public static void main(String[] args) {
//		 java.util.Date today = new java.util.Date();
//		 System.out.println("今天的日期是" + today);
		 
		 // import java.text.DateFormat; 
		 // import java.util.Date;
		 Date date = new Date();
		 DateFormat formatdate = DateFormat.getDateInstance(DateFormat.FULL);
		 DateFormat formatdatetime = DateFormat.getDateTimeInstance();
		 System.out.println(formatdate.format(date));
		 System.out.println(formatdatetime.format(date));
	 }
	 
	 
	 // 类的路径
	 
	 public void test () {
		 
		 // 引用了其他包的类，需要 import
		 array arr = new array();
		 
		 // 引用了本包下面的其他类, 不需要import
		 Person p = new Person("linsheng",18);
		 
		  
		 
	 }
	 
	 /*补充：
	  * 一个java文件中可以定义多个类，但是最多只有一个类被public修饰，并且这个类的类名与文件名必须相同
	  * 一个java文件中可以定义多个非 public 类
	  * 
	  * */
	 
	 
	 

}

    
```