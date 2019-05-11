
```java
	package Object;

public class Person {

	// -----------------------------------类的创建和实例化----------------------------------

	/*
	 * package 后面的为包名
	 * 
	 * class 后面的 为 类名，public 为类的修饰符，表明该类是公共类，可以被其他类访问。
	 * 
	 */

	// 成员变量
	String name;
	int age;

	// 函数
	void walk() {
		System.out.println("走路");
	}

	// 构造方法
	// 规范是方法的名称必须与类名相同，并且没有返回值。
	// 每个类都有构造方法。如果没有显式地为类定义构造方法，Java编译器将会为该类提供一个默认的构造方法

	/*
	 * 补充：
	 * 
	 * 在构造方法中调用另一个构造方法，调用动作必须置于最起始的位置。
	 * 不能在构造方法以外的任何方法内调用构造方法。
	 *  在一个构造方法内只能调用一个构造方法。
	 * 
	 */

	Person(String name1, int age1) {
		name = name1;
		age = age1;
	}

	public static void main(String arg[]) {
		// 创建对象时传递的参数要与构造方法参数列表对应
		Person p = new Person("linsheng", 18);
		System.out.println(p.name);
		System.out.println(p.age);

		/*
		 * 在Java中，使用new关键字来创建对象，一般有以下三个步骤： 
		 * 声明：声明一个对象，包括对象名称和对象类型。 
		 * 实例化：使用关键字new来创建一个对象。
		 * 初始化：使用new创建对象时，会调用构造方法初始化对象。
		 * 
		 * Dog myDog; // 声明一个对象 myDog = new Dog("花花", 3); // 实例化 Dog myDog = new
		 * Dog("花花", 3); // 声明的同时实例化
		 */

		// 访问成员变量和方法 用点语法
		int age = p.age;
		p.walk();

	}

}
    
```