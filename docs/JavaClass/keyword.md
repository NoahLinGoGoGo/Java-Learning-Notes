
```java
	
/*
 * 修饰符
 * 
 * Java中的是修饰符 包括 访问修饰符 和 非访问修饰符
 * 
 * 访问修饰符： 也叫控制修饰符，是能控制类，成员变量，方法的使用权限的关键字
 * 
 * 
 * Java 中有四种不同的访问权限：
 *  1. public: 对所有类可见 
 *  2. protected: 对同一个包内的类和他的子类可见 
 *  3. private: 在本类里可见 
 *  4. 默认：视具体情况而定
 * 
 * 
 */

// public 修饰符

//	public static void main(String[] arguments) {
//		// 每个类的 main() 方法必须设置成共有的，否则，Java 编译器不能运行该类
//	}

/*
 * java中的main()方法 表明：说明这是个java应用程序，通过JVM直接启动运行的程序
 * 
 */

// protected 修饰符

/*
 * 被声明为protected的变量、方法和构造方法能被同一个包中的任何其他类访问，也能够被不同包中的子类访问。
 * 
 * protected访问修饰符不能修饰类和接口，方法和成员变量能够声明为protected，但是接口的成员变量和成员方法不能声明为protected。
 * 
 * 子类能访问protected修饰符声明的方法和变量，这样就能保护不相关的类使用这些方法和变量。
 * 
 * 下面的父类使用了protected访问修饰符，子类重载了父类的bark()方法。
 * 
 */


public class KeyWord {
	
	// private
	private String name;
	
	public String getName() {
		return name;
	}
	
	public void setName(String name) {
		this.name = name;
	}

	// public
	public static void main(String arg[]) {
		System.out.println("i am superclass");
	}

	//  protected
	protected void walk() {
		System.out.println("superclass walk");
	}

}

//   private 修饰符
/*
 * 私有访问修饰符是最严格的访问级别，所以被声明为private的方法、变量和构造方法只能被所属类访问，并且类和接口不能声明为private。
 * 
 * 声明为私有访问类型的变量只能通过类中公共的Getter/Setter方法被外部类访问。
 */


/* 默认修饰符
 * 
 * 不使用任何修饰符声明的属性和方法，对同一个包内的类是可见的。
 * 接口里的变量都隐式声明为public static final，而接口里的方法默认情况下访问权限为public
 * 
 * */


/*
 * 访问控制和继承的规则：
 * 
 * 父类中声明为 public 的方法在子类中也必须为 public
 * 父类中声明为 protected 的方法在子类中可以为 protected 或 public
 * 父类中声明为 private 的方法 子类无法继承
 * 父类中默认修饰符声明的方法在子类中可以声明为 pivate
 * 
 * 
 * */

 
 package Object;

public class SubKeyWord extends KeyWord {

	 public static void main(String arg[]) {
	    System.out.println("i am subclass");
	 }
	 
	 protected void walk() {
		 System.out.println("subclass walk");
	 }
	  
	  
}
    
```