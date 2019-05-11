
```java
	package Object;

public class Inherit extends Person {
	public static void main(String arg[]) {
		System.out.println("i am inHherit, subclass of Person");
		
		Dog dog = new Dog("花花",3);
		dog.say();
	}

	// -----------------------------------类的继承---------------------------------------

	// 继承的关键字： extends
	
	// java中类的继承是 单继承， 即一个类只能有一个父类
	
	

	// 构造方法不能被继承,如果父类有构造方法，子类必须重写父类的构造方法，不然会报错
	Inherit(String name1, int age1) {
		super(name1, age1);
		// TODO Auto-generated constructor stub
	}
	
	/*super 关键字的功能：
	 * 1. 调用父类声明为 private 的变量
	 * 2. 点取已经覆盖了点的方法
	 * 3. 作为方法名表示父类的构造方法
	 * 
	 * 
	 * 注意 super 与 this 的区别：super 不是一个对象的引用，
	 * 不能将 super 赋值给另一个对象变量，
	 * 它只是一个指示编译器调用父类方法的特殊关键字
	 * */

	// 重写父类的属性，方法 
	String name;

	void walk() {
		System.out.println("走路");
	}

	
//	---------------------------------方法的覆盖和重载----------------------------------
	
	
	/*
	 * 方法覆盖：
	 * 1. 方法覆盖的返回类型，方法名称，参数列表必须与原方法一毛一样
	 * 2. 覆盖方法访问权限不允许缩小
	 * 3. 覆盖方法不能比原方法抛出更多的异常
	 * 4. 有几种情况方法是无法覆盖的，父类中的方法是 final, private, static
	 * 
	 * 
	 * 方法的重载
	 * 重点是参数个数，参数类型，参数顺序不一样就构成重载
	 * 
	 *
	 * */


}


class Animal{
    String name;
    public Animal(String name){
        this.name = name;
    }
    
    protected void bake() {
    	System.out.println("dong  dong  dong");
    }
}
class Dog extends Animal{
    int age;
    public Dog(String name, int age){
        super(name);
        this.age = age;
    }
    public void say(){
        System.out.println("我是一只可爱的小狗，我的名字叫" + name + "，我" + age + "岁了");
    }
    
    protected void bake() {
    	super.bake();
    	System.out.println("wang  wang  wang");
    }
}

/*
 * 从上面的代码可以得到：
 * 1.在构造方法中调用另一个构造方法，调用动作必须置于最起始的位置。
 * 2.不能在构造方法以外的任何方法内调用构造方法。
 * 3.在一个构造方法内只能调用一个构造方法。
 * 
 * */




    
```