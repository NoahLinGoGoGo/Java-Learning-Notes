
```java
	/*
	 * Java 是一种强类型的语言，声明变量时必须指明数据类型
	 * 
	 * java 中共有8 中强类型的语言，分别是： 整型： Java 不支持无符号类型(unsigned) 占位符%d 字节型 byte (占内存 1
	 * byte) 短整型 short (占内存 2 bytes) 整型 int (占内存 4 bytes) 长整型 long (占内存 8 bytes)
	 * 
	 * 浮点型： 占位符%f 单精度 float (占内存 4 bytes) 双精度 double (占内存 8 bytes)
	 * 
	 * 字符型： char (占内存 2 bytes) 字符型数据只能是一个字符，由单引号包围 占位符%c 字符串 %s 布尔型： boolean (占内存 1
	 * bytes) true/false
	 * 
	 * 
	 */

	public static void main(String[] args) {

		// ------------------------------------基本数据类型------------------------------------------

		// 整型
		short s = 22;
		int m = 022;
		long n = 0x22;
		System.out.println("转化成十进制：s = " + s + ", m = " + m + ", n = " + n);

		// float
		// (最长位数7位，包括小数部分)
//		 float x = 99.9;  // 报错： cannot convert from double to float
		float y = 200.00f;
		float z = 356.111F;
		System.out.printf("y = %f, z = %f\n", y, z);

		// double
		// 不带任何标志的浮点型数据，系统默认是 double 类型
		double a = 22.22;
		double b = 333.333D;
		double c = 4444.4444d;
		System.out.printf("a = %f, b = %f, c = %f\n", a, b, c);

		// 字符型
		char firstName = '林';
		char lastName = '升';
		System.out.println("my name is " + firstName + lastName);

		// ------------------------------------数据类型转换------------------------------------------

		/*
		 * 两种方式 自动转换： 程序在执行过程中IDE进行的转换，一般“低位”向“高位”转换， byte,short,char-> int -> long ->
		 * float -> double
		 * 
		 * 强制转换： 程序员手动转换 格式： (数据类型)被转类型
		 */

		// 强制转换

		int xx;
		double yy;
		xx = (int) 34.56 + (int) 11.2; // 丢失精度    变成了 34 + 11 
		yy = (double) xx + (double)10 + 1; // 提高精度   45.0 + 10.0 + 1
		System.out.println("xx=" + xx);
		System.out.println("yy=" + yy);
    
```