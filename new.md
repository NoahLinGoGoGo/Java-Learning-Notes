[TOC]

# 核心实践派

##  数组
```java
import java.util.List; 
/*
List：一种有序列表的集合的接口，例如，按索引排列的Student对象的List；
java.util.Set：一种保证没有重复元素的集合的接口，例如，所有无重复名称的Student对象的Set；
*/
import java.util.ArrayList;
import java.util.Collections;

List<String> hotWords = new ArrayList<>();

hotWords.add("carrot");
hotWords.add("tomato");
hotWords.add("patato");
/*
遍历数组
方式1：使用标准的for循环
方式2：for each
方式2：Arrays.toString()打印
*/
for (int i = 0; i < hotWords.size(); i ++) {
    String value = hotWords.get(i);
    System.out.println(value); // carrot\n tomato\n patato\n
}
/*
数组排序
1.对于String或Integer这些已经实现Comparable接口的类来说，可以直接使用Collections.sort方法传入list参数来实现默认方式（正序）排序；

2.如果不想使用默认方式（正序）排序，可以通过Collections.sort传入第二个参数类型为Comparator来自定义排序规则；
        Collections.sort(intList,new Comparator<Integer>() {
            @Override
            public int compare(Integer o1, Integer o2) {
                // 返回值为int类型，大于0表示正序，小于0表示逆序
                return o2-o1;
            }
        });
*/
Collections.sort(hotWords);
for (String value : hotWords) {
    System.out.println(value);  // carrot\n  patato\n tomato\n
}
//hotWords.addAll(list2);
//hotWords.remove(0);
//hotWords.clear();

// 上面的hotWords准确的叫法是集合，下面两个定义才是真正的数组，不过下面的相比在开发中用得少
char[] helloArray = { 'h', 'e', 'l', 'l', 'o'}; // 注意是 小括号
int[] pixels = new int[256]; // 固定大小数组，长度256
helloArray = null;

```
##  字符串, Java中String是个对象
```java
import java.lang.String;

String keyword = mInputBox.getText().toString().trim(); // trim() 方法用于删除字符串的开头和结尾的空白字符

String packageName = "com.ximalaya.guangzhou";
System.out.println(packageName.length());  // 22
System.out.println(packageName.charAt(3));  // . index从0开始
System.out.println(packageName.equals("com.ximalaya.guangzhou")); //true
System.out.println(packageName.endsWith("com")); // false
System.out.println(packageName.startsWith("com")); // true
System.out.println(packageName.replace("guangzhou","shenzhen")); //com.ximalaya.shenzhen
System.out.println(packageName.toLowerCase()); //com.ximalaya.guangzhou
System.out.println(packageName.toUpperCase()); //COM.XIMALAYA.GUANGZHOU
System.out.println(packageName.contains("ximalaya")); //true
System.out.println(packageName.isEmpty()); // false
System.out.println(packageName.substring(3)); // .ximalaya.guangzhou, 包含 fromindex
// 等等API
```
##  Map

`Map`这种键值（key-value）映射表的数据结构，作用就是能高效通过`key`快速查找`value`（元素）。和`List`类似，`Map`也是一个接口，最常用的实现类是`HashMap`

```java
import java.util.HashMap;
import java.util.Map;

Map<String,String> map = new HashMap<>();

map.put("username","John"); 
map.put("password","123456"); 

System.out.println(map.get("username"));  // John
System.out.println(map.containsKey("password")); // true

//遍历enumerate KEY, 注意不保证顺序
for (String key : map.keySet()) {
    System.out.println(key); 
}

//遍历enumerate KEY和VALUE, 注意不保证顺序
//for (Map.Entry<String, Integer> entry : map.entrySet()) {
    //String key = entry.getKey();
    //Integer value = entry.getValue();
    //System.out.println(key + " = " + value);
//}

```