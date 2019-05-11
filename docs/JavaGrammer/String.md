
```java
	// 定义字符串
//		String strName = new String("string content"); // 套用数组的定义，繁琐
		String url = "http://www.baidu.com";
		
		// String字符串与数组有一个共同点，就是它们被初始化后，长度是不变的，并且内容也不变。
		// 如果要改变它的值，就会产生一个新的字符串
		
		String str = "Hello ";
		System.out.println("str 修改之前的地址 " + System.identityHashCode(str));
		str += "World";
		System.out.println(str);
		System.out.println("str 修改之后的地址 " + System.identityHashCode(str));

		
		// 字符串长度  length()
		System.out.println(str.length());
		
		// 根据索引取字符 charAt()
		System.out.println(str.charAt(5));
		
		// 包含字符串 contains()
		if (url.contains("http")) {
			System.out.println("url是合法的");
		}
		
		// 替换字符串  replace(oldChar, newChar)
		String newUrl = url.replace("http", "https");
		System.out.println(newUrl);
		
		// 拆分字符串 split()
		String strArr[] = str.split("l");
//		System.out.println(Arrays.toString(strArr));
		for(String strr: strArr) {
			System.out.println(strr);
		}
		
		
/*
 * 本文打印：
str 修改之前的地址 929338653
Hello World
str 修改之后的地址 1259475182
11
 
url是合法的
https://www.baidu.com
He

o Wor
d
 * 
 * 
 * */

    
```