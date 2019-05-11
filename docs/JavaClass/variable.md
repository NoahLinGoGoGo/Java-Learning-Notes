
```java
	package Object;

public class Variable {
	
	 //------------------------变量的作用域----------------------
	 
	 // java 中的变量作用域和其他语言相似。比如 { } 里面的变量出 { } 就消失了
	
	
	// 类级变量,也叫全局变量/静态变量，用static修饰。 不需要实例化。通过类名访问。
//	public static String name;
	public static String name = "linsheng";
	
	
	
	
	public int age;  // 对象的成员变量，通过对象的实例来访问
	
	
	
	
	
	
	
	
	 //------------------------this 关键字----------------------
	
	// this 关键字用来表示当前对象本身，或当前类的一个实例，可以通过this来访问对象的所有方法和属性
	int x = 10;
	int y = 15;
	
	int sum() {
		return this.x + this.y;
	}
	
	
	// 使用this区分同名变量
	void demo (int x, int y) {
		this.x = x;
		this.y = y;
	}
	
	// 还作为参数传递
	
	
	
	
	 //-----------------------------------方法重载（method overloading）---------------------------------
	
	
	// 方法重载定义：在Java中，在同一个类中的多个方法有相同的名字，但是参数列表不同。
	
	// 参数列表不同：包括参数类型不同，参数的个数不同，参数的顺序不同，只要有一个不同就叫做参数列表不同
	
	 // 一个普通的方法，不带参数
    void test(){
        System.out.println("No parameters");
    }
    // 重载上面的方法，并且带了一个整型参数
    void test(int a){
        System.out.println("第一个参数: " + a);
    }
    // 重载上面的方法，并且带了两个参数
    void test(int a,int b){
        System.out.println("第一个参数 and 第二个参数: " + a + " " + b);
    }
    // 重载上面的方法，并且带了一个双精度参数
    double test(double a){
        System.out.println("第一个参数: " + a);
        return a*a;
    }
   
    public static void main(String args[]){
        Variable obj= new Variable();
        obj.test();
        obj.test(2);
        obj.test(2,3);
        obj.test(2.0);
    }
	
    /*说明：
     * 跟成员方法一样，构造方法也可以不同
     * 声明为 final 的方法不能被重载
     * 声明为 static 的方法不能被重载，但是能够被再次声明
     * 
     * 
     * 方法重载的规则：
     * 方法名必须相同
     * 参数列表必须不同（顺序，类型，个数不同）
     * 对返回值没有限制，可以相同，可以不同，换句话说，只有返回类型不同不叫方法重载
     * 
     * */
	
	
	
/*本文打印：
No parameters
第一个参数: 2
第一个参数 and 第二个参数: 2 3
第一个参数: 2.0

 * 
 * */


}

    
```