# Java程序的组织结构

- JAVA程序是由类和接口组成的。

- **一个简单的java程序，有一个类即可**

- 一个简单的类，可以仅包含一个入口方法`public static void main(String[] args)`，结构如下：

```

public class ClassName {

    public static void main(String[] args) {

        //do something

    }

}

```

- 一个比较完整的java程序包含以下部分：

    - package语句

    - import语句

    - public Class Definition    //公共的类定义部分，至少只有一个公共类的定义

    //java规定该java源程序的文件名必须和该公共类名完全一致

    - Class Definition    //类定义部分，可以有0个或多个

    - interface Definition    //接口的定义部分，可以有0个或者多个

- 一般来讲，具有相同功能的类放在一个package中。

- 一个java源程序最多只能有一个公共类(public)的定义

- java源程序文件必须和公共类的名字相同;如果没有定义公共类，文件名可以取任意名

- 如果一个源程序有多个类定义，则在编译时将为每个类生成一个.class文件（以类名为文件名，以.class作为扩展名）

- java源文件又叫做编译单元。一个java文件包含多个类，但至少包含一个public类，作为java文件的公共接口，公共类的名字和源文件的名字相同，但后缀为.java

- 在一个java文件中，在不同的类中，是可以有多个`public static void main(String[] args)`，但是对于java程序来讲，只需要一个入口，也就是只需要有一个类包含main方法，而其他的类都是用于被main方法直接或者间接调用

- `public static void main(String[] args)`不是必须要放在public类中，比如：

```

package lc01;



class Dog{ 



   Dog(){ 

       System.out.println("I'm a dog."); 

   } 



   public static void main(String[] args){ 



       new Dog(); 

       new Cat(); 

   } 

} 



class Cat{ 



   Cat(){ 

       System.out.println("I'm a cat."); 

   } 

}  

```

