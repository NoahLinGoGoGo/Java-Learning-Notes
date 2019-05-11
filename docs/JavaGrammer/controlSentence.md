
```java
	/*
		 * C里面常用的流程控制语句类似，例如：
		 * if, if...else, if...else if...,do ...while, for,switch..case 该有的都有啦！！！
		 * 
		 * */

		// 没有倒三角的身材，只有打印一个了
		for (int i = 0; i < 9; i++) {
			for (int j = 0; j < 9 - i; j++) {
//				 System.out.println("i = " + i + ", j = " + j);
				 if (i <= j) {
					 System.out.print("*");
				 } else {
					 System.out.print(" ");
				 }
			}
				 System.out.print("\n");
		}
		
		
		// 没有break会穿透 
		int n = 1;
		switch (n) {
		case 0:
			 System.out.println("0");
//			break;
		case 1:
			 System.out.println("1");
//			break;
		case 2:
			 System.out.println("2");
//			break;
		 default:
	         System.out.println("default");
		}
		
		/*
		 * 本文打印： *********
		 *******
		 *****
		 ***
		 *
		 * 
		 * 
		 * 
		 * 
		 * 1 2 default
		 * 
		 * 
		 */
    
```