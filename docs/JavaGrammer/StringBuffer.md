
```java
		/*
		 * 在Java中，String是不可变字符串，而且操作效率低下
		 * StringBuffer 可以理解成可变字符串，默认是16个字节长度的缓冲区   多线程安全
		 * 
		 * */
		
		// 创建StringBuffer
		StringBuffer str1 = new StringBuffer(); // 16个字节长度的缓冲区
		StringBuffer str2 = new StringBuffer(512); // 512个字节长度的缓冲区
		StringBuffer str3 = new StringBuffer("www.baidu.com"); // 在缓冲区存放了“www.baidu.com”，并且预留了16个字节长度的空缓冲区

		System.out.println("str1 修改之前的地址 " + System.identityHashCode(str1));
		System.out.println("str2 修改之前的地址 " + System.identityHashCode(str2));
		System.out.println("str3 修改之前的地址 " + System.identityHashCode(str3));

		
		// 末尾添加字符串 append()
		str1.append("lin sheng");
		
		// 删除字符串 delete()
		str3.delete(0, 3);  // 删除索引为 [0,3) 的字符串
		str3.deleteCharAt(0); 
		System.out.println("str3 删除索引为 [0,3) 的字符串的内容 " + str3);

		// 插入字符串
		str3.insert(0, "www.");
		System.out.println("str3 插入修改后的字符串的内容 " + str3);
		
		// 替换字符 setCharAt()
		str3.setCharAt(4, '.');
		// 替换字符串
		str3.replace(5, 9, "zhihu");
		
		System.out.println("str3 替换字符串后的字符串的内容 " + str3);
		

		System.out.println("str1 修改之后的地址 " + System.identityHashCode(str1));
		System.out.println("str2 修改之后的地址 " + System.identityHashCode(str2));
		System.out.println("str3 修改之后的地址 " + System.identityHashCode(str3));


		// 补充： StringBuilder  可变字符串  线程不安全
		StringBuilder str4 = new StringBuilder(1024);
		System.out.println("str4 修改之前的地址 " + System.identityHashCode(str4));
		str4.append("000000");
		System.out.println("str4 修改之后的地址 " + System.identityHashCode(str4));
		
		
		
    
```