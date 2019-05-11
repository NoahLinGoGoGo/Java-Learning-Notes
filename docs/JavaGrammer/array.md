
```java
	/* Java中的数组是可以存放任意数据类型，包括基本类型和组合类型
		 * 静态数组一旦声明或初始化后容量就固定了，不能改变。
		 * 如果需要改变容量，就需要用到数组列表（动态数组ArrayList）或者向量（Vector）
		*/
		
		// 定义数组
		int demoArray[];
		double[] demoArray2;
		
		// 数组赋值，分配内存
		demoArray = new int[5];
		demoArray2 = new double[0];
		
		// 数组初始化
		int intArray[] = {1,2,3,4};
		String stringArray[] = {"11111","222222","33333333"};
		
		// 动态初始化
		float floatArray[] = new float[3];
		floatArray[0] = 1F;
		floatArray[1] = 2.f;
		floatArray[2] = 3f;
		
		// 数组引用
		System.out.println(floatArray[0]);  
		
		// 数组长度
		System.out.println(floatArray.length);  
		
		// 数组遍历
		for(int i = 0; i < stringArray.length; i++) {
			System.out.println(stringArray[i]);
		}
		
		for(String str: stringArray) {
			System.out.println(str);
		}
		
		// 二维数组
		int arr[ ][ ] = { {1,2}, {3,4,5}, {6,7} };
		int a[ ][ ] = new int[2][3];
		a[0] = new int[3];
		a[0][1] = 34;
		
		
		/*
 * 本文打印：
1.0
3
11111
222222
33333333
11111
222222
33333333
 * 
 * */
    
```