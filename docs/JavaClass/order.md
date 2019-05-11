
```java
	package Object;

public class ExecutionOrder {

	
	//------------------------------一个基本的 Java 类的运行顺序--------------------------------
	
	private String name;
	private int age;
	
	private ExecutionOrder() {
		this.name = "linsheng";
		this.age = 18;
	}
	
	 public static void main(String[] args){
		 ExecutionOrder obj = new ExecutionOrder();
	     System.out.println(obj.name + "的年龄是" + obj.age);
	     obj.convert();
	 }
	 
	 
	 /*基本运行顺序是：
	  * 1. 16行 main()函数入口  
	  * 2. 17行 运行ExecutionOrder构造函数
	  * 3. 进入11行后，跳到第8和第9行执行，这是因为初始化一个类，必须先初始化他的属性
	  * 4. 属性初始化完成后，回到构造方法，执行里面赋值第12和第13行
	  * 5. 17 行执行完后就是顺序执行直到大括号结束，main方法执行完毕。
	  * 
	  * */
	 
	 
	//------------------------------Java包装类，拆箱和装箱--------------------------------
	
	 
	/*什么叫包装类，拆箱和装箱？
	 * 
	 * 简单的说，就是把基本数据类型转换为对象类型，Java 为每种基本数据类型分别设计了对应的类，称之为包装类（Wraper Classes）
	 * 装箱：基本类型 转换为 包装类 称为 装箱。反过来称为拆箱。
	 * 
	 * 
	 * 下面是基本数据类型和包装类的对应关系：
	 * byte -> Byte
	 * short -> Short
	 * int -> Integer
	 * long -> Long
	 * char -> Character
	 * float -> Float
	 * double -> Double
	 * boolean -> Boolean
	 * 
	 * 总结： 基本上是首字母大写，简写化成全称
	 * */ 
	 
	 
	 public void convert () {
		 
		 
		 
		 
		 // int 和 Integer 相互转换
		 int m = 500;
//		 Integer obj = new Integer(m);  过期警告⚠️
		 Integer obj =Integer.valueOf(m);   // 装箱
		 int n = obj.intValue();            // 拆箱
		 System.out.println("n = " + n);
		 
		Integer obj2 = 500;
		System.out.println("obj 等价于 obj2 ?" + obj.equals(obj2));
//		System.out.println("obj 保存的内存地址是 " + System.identityHashCode(obj));
//		System.out.println("obj2 保存的内存地址是 "+ System.identityHashCode(obj2));
		
		
		
		
		
		// 字符串 转换为 整数 
		Integer number = Integer.parseInt("99"); // parseInt 可以选进制
		// 判断什么样的字符串可以转换为整数
		 String str[] = {"123", "123abc", "abc123", "abcxyz"};
	        for(String str1 : str){
	            try{
	                int a = Integer.parseInt(str1, 10);
	                System.out.println(str1 + " 可以转换为整数 " + a);
	            }catch(Exception e){
	                System.out.println(str1 + " 无法转换为整数");
	            }
	        }
	        
	        
	        
	        
	    // 整数  转换为 字符串
	    String s = Integer.toString(500);
	    System.out.println(s);
	    
	    
	    // 上面的例子都是手动拆箱装箱，Java 1.5 之后可以自动拆箱装箱，下面是例子
	    int x = 100;
	    Integer y = x;  // 自动装箱
	    int z = y;    // 自动拆箱
	    System.out.println("z = " + z);
	 }
}


/*
 * 本文打印：
linsheng的年龄是18
n = 500
obj 等价于 obj2 ?true
123 可以转换为整数 123
123abc 无法转换为整数
abc123 无法转换为整数
abcxyz 无法转换为整数
500
z = 100
 * 
 * */


    
```