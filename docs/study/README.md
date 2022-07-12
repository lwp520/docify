





### 1. 面向过程和面向对象的区别

![1578188002122](C:/Users/%E6%B5%81%E6%B5%AA/Desktop/%E5%BC%80%E5%A7%8B/docs/imgs/1578188002122.png)

面向过程（Procedure Oriented）:

​	面向过程分析的是解决问题的实现步骤，然后由自己一步一步去完成。

​	对应程序来说：主方法-->方法1--->方法2-->方法3

​				张三---->订票---->订酒店

​	所以说：程序的性能比面向对象的要高，但是程序不易复用

面向对象（Object Oriented）

​	面向对象分析的不是解决问题的步骤，而是这个问题有“谁”解决，“谁”在这里指的就是对象

​       对应程序来说：

​	对象1---->对象2负责解决问题

​        张三----->行政人员：1.订机票 2.订酒店

​	李四----->行政人员：1.订机票 2.订酒店

​	所以说：面向对象的性能比面向过程要低，但是程序的复用性更好

### 2.  类的介绍和定义

1. 类的介绍

   类是java中的最小的基本单位。

   类是对具有共同**属性**和**行为**事物的抽象。

   总结：属性其实就是类的变量，行为其实就是类的方法

   比如：张三要去北京出差，由行政人员负责订机票，订酒店。

   ​    行政人员：

```
  1.   **机票务供应商**

  2.   **酒店供应商**

  3.   订机票

  4.   订酒店

       总结：

       ​	 机票，酒店供应商就是行政人员的属性

       ​	 订机票，订酒店就是行政人员的行为

       ​         行政人员称之为一个类
```

   比如：手机

   ​	共同属性：价格和品牌

   ​	共同行为：打电话和发短信

1. 类的定义

   语法格式：

   ​		public  class 类名{

   ​				属性

   ​				行为

   ​                 }

   类的定义：

   ```java
   package com.it.se7.lesssion1;
   /*
       演示：定义一个手机类
           1.属性： 品牌，价格
           2.行为： 打电话，发短信
    */
   public class Phone {
       //1.手机的属性
        String  brand;//品牌
        double price;//价格
       //2.手机的行为
       public  void sendMessage(){
           System.out.println("发短信");
       }
       public void callOther(){
           System.out.println("打电话");
       }
   }
   
   ```

   类的使用：

   ```java
   package com.it.se7.lesssion1;
   
   /**
    * 演示：手机的测试类
    */
   public class DemoPhone {
       public static void main(String[] args) {
           //需求：通过手机打电话或者发短信
           //1.买手机--付钱
                Phone huiweiPhone  = new Phone();//买手机，new 个对象
                huiweiPhone.price=2880.8;//付钱
           //2.买手机以后---打电话或者发短信
               huiweiPhone.sendMessage();//通过对象，调用方法
       }
   }
   ```

2. 类和对象的关系:

   - 类：是对具有共同属性和行为事物的抽象

   - 对象：看得见摸得着具体实体。

     在java开发中，得到对象：类  对象 =  new 类（）；

     回顾一下java的类型：

     1. java的基本类型
     2. java的引用类型：在开发中，由程序员定义的类都是引用类型，都可以new(都可以创建对象)

### 3.对象的创建和使用

1. 对象概述

   对象是对一个类的实例化，直白的来说对象就是类的具体体现。

   比如：

   ​	手机类Phone(抽象)

   ​	去对手机类Phone的实例化（买一个具体品牌和对应价格的手机）

   ​	Phone   huaweiPhone = new Phone();//huweiPhone就是一个对象，就是对Phone的实例化

   ​	Phone   applePhone  = new Phone();//applePhone就是一个对象，就是对Phone的实例化

2. 对象能做什么，具体怎么体现

   对象的属性： 类里面定义的属性

   对象的行为： 类里面定义的行为

   步骤一：对类进行实例化（创建一个对象，或者得到一个实例）

   ​		类名  对象 = new 类名（）;

   ​		比如：Phone  huaweiPhone = new Phone();

   步骤二：通过对象操作对象的属性和行为

   ​		类里面：定义的属性  和  行为 （对具有共同特性事务的抽象）

   ​		操作属性和行为：通过类的具体体现去操作，其实就是通过对象来操作属性和行为。

   ​		操作属性： 

   ​				对象.属性=值；//给属性设置值

   ​	       		数据类型 变量名称 = 对象.属性；//获取值

   ​		操作行为： 

   ​				对象.方法名称（参数）；

```java
package com.it.se7.lesssion1;

/**
 * 演示：对象的使用
 *  步骤一：得到对象（new）
 *              类名 对象 = new 类名（）；
 *  步骤二：使用对象
 *              对象.属性 = 值；//设置值
 *              类型 变量名称 = 对象.属性；//获取值
 *              对象.方法名称（）;
 */
public class DemoPhone2 {
    public static void main(String[] args) {
        //1.创建一个具体的手机对象，比如 ：applePhone
        Phone applePhone = new Phone();
        //2.操作属性：设置变量
        applePhone.brand="苹果手机";
        applePhone.price=8888.88;
        //2.1 获取属性的值：获取变量的值
        String b = applePhone.brand;
        double price = applePhone.price;
        System.out.println("获取属性的值："+b+" "+ price);
        //3.操作行为：调用方法
        applePhone.sendMessage();
        applePhone.callOther();
    }
}
```

案例：创建一个Student类

​	  共同属性：name , age--

​	  共同行为： study(), findJob();--

步骤一：创建一个类，public class Student{属性;行为};

步骤二：定义具体的属性和方法

```java
package com.it.se7.lession2;

/**
 * 演示：定义一个学生类
 */
public class Student {
    //1.属性：变量
    String name;
    int  age;
    //2.行为：方法
    public void  study(){
        System.out.println(name+",在认真刻苦的学习");
    }
    public void findHighSalayJob(){
        System.out.println(name+","+age+",年级轻轻，就找到一个高薪的工作");
    }

}

```

```java
package com.it.se7.lession2;

/**
 * 演示：学生对象的使用
 */
public class DemoStudent {
    public static void main(String[] args) {
        //1.创建一个学生对象
        Student  st = new Student();
        //2.操作属性： 给变量设置值
        st.name="游涛";
        st.age=19;
        //3.操作行为： 调用方法
        st.study();
        st.findHighSalayJob();
    }
}

```

### 4.对象在jvm内存中的分配和管理

- 单个对象在jvm内存中的分配和管理

  - 回顾jvm内存的五块空间

    - 栈： 存的方法（方法进栈和出栈）
    - 堆：存的对象
    - 方法区：存的类。类里面的所有信息都在方法区，比如：类的属性和方法
    - 本地方法栈：这块是其它语法编写的，作用：运行方法区
    - 寄存器：与cpu相关的指令

  - 单个对象在jvm内存中情况：

    ![1578195564853](C:/Users/%E6%B5%81%E6%B5%AA/Desktop/%E5%BC%80%E5%A7%8B/docs/imgs/1578195564853.png)

  - 多个对象在jvm内存中分配的情况：

    ![1578196146320](C:/Users/%E6%B5%81%E6%B5%AA/Desktop/%E5%BC%80%E5%A7%8B/docs/imgs/1578196146320.png)

  - 将一个对象赋值个另一个对象在jvm内存中的分配情况

    ![1578196591320](C:/Users/%E6%B5%81%E6%B5%AA/Desktop/%E5%BC%80%E5%A7%8B/docs/imgs/1578196591320.png)

### 5.成员和局部变量

- 成员变量概述

  在类的内部，在方法外部定义的变量称之为成员变量.

- 局部变量概述

  在方法内部定义的变量称之为局部变量。

- 成员变量和局部变量的区别

  - 1.从定义位置来说：

    成员变量在方法外部，局部变量在方法外部

  - 2.从使用范围来说

    成员变量在类的任意位置使用，局部变量只能在定义的方法内部使用

  - 3.从初始化值来说

    成员变量都有默认值（初始值），具体初始值是什么，和成员变量的数据类型有关，

    比如: String name;//name=null;

    ​	 int   age;// age=0

    如果成员变量的类型是引用类型，初始值都是null

    如果成员变量的类型是基本类型，初始值是数字或者boolean值或者**' '**

    局部变量没有默认值

​        具体区别，详见下图：

![1578207175634](C:/Users/%E6%B5%81%E6%B5%AA/Desktop/%E5%BC%80%E5%A7%8B/docs/imgs/1578207175634.png)

![1578208785903](C:/Users/%E6%B5%81%E6%B5%AA/Desktop/%E5%BC%80%E5%A7%8B/docs/imgs/1578208785903.png)

注意：

1. 成员变量和局部变量的名称相同，在方法内部使用变量时，根据就近原则，使用的局部变量
2. 成员变量和局部变量的名称相同，在方法内部使用变量时，确定使用成员变量，使用this来区分

### 6.this

1. this概述

   this表示当前类的对象引用，直白的来说，“谁”调用方法"谁就是" this.

2. this作用：

   使用this来区分成员变量和局部变量。

![1578209994203](C:/Users/%E6%B5%81%E6%B5%AA/Desktop/%E5%BC%80%E5%A7%8B/docs/imgs/1578209994203.png)

### 7.封装和private

1. 封装概述

   - 概述

     封装可以被认为是一个保护屏障，将类中的属性、行为等数据给隐藏起来，

     防止该类的数据被外界的代码随机访问。

   - 封装在代码中的具体体现

     - 将属性（成员变量）给封装到类中，给私有化
     - 将行为（成员方法）给封装到类中，给私有化

   - 将类中的属性和行为给隐藏起来，加个“围栏”

     在这里的操作，使用“围栏”，哪个围栏就是**访问修饰符**。

     常见的访问修饰符：

     - public(公共的) : 如果属性和行为被public修饰，在外界可以被访问到。

     - private(私有的):如果属性和行为被private修饰，在外界不可以被访问到。

     - 比如：

     - ```java
       /**
        * 演示：定义一个花园类
        */
       public class Gardon {
           private  String grass;//私有的草坪
           private void play(){//私有的方法
               System.out.println("在花园的"+grass+"玩耍");
           }
       }
       
       ```

     - 被private修饰的方法和属性，在外界访问，是不允许的

     - ![1578214287281](C:/Users/%E6%B5%81%E6%B5%AA/Desktop/%E5%BC%80%E5%A7%8B/docs/imgs/1578214287281.png)

2. private

   - 概述

     private是一个访问修饰符，private可以用在类的属性（成员变量）、类的行为（成员方法）

     表示该类的属性和行为不能被外界访问。

     当然可以在类的内部使用，比如下图：

     ```java
     /**
      * 演示：定义一个花园类
      */
     public class Gardon {
         private  String grass;//草坪
         private void play(){//玩
             System.out.println("在花园的"+grass+"玩耍");
         }
     
         public static void main(String[] args) {
             Gardon gardon = new Gardon();
             gardon.play();
         }
     }
     
     ```

   - 类的属性和行为被private修饰了，在外界使用

     - 在类里面被private修饰的属性，在外界使用，可以“搭桥”

       这个“搭桥”指的给该属性提供被public修饰的方法操作这个属性。

       语法格式：

       public  class 类名{

       ​		private  String  属性名称;

       ​		//搭桥：给属性设置值

       ​		public void  **set**属性名称(String  sendValue){ 属性名称 = sendValue}

       ​		//搭桥：获取属性的值

       ​		public  String  **get**属性名称(){return 属性名称；}

       }

     - 在类里面被private修饰的方法，在外界使用，可以“开路”，使用java提供的反射技术（后面讲）

     ```java
     package com.it.se7.lession6;
     
     /**
      * 演示：定义一个花园类
      */
     public class Gardon {
         private  String grass;//私有的草坪
         //搭桥：给该属性设置值
         public  void  setGrass(String sendValue){//提供公开的setXXX（）方法
             grass = sendValue;
         }
         //搭桥：获取该属性的值
         public  String getGrass(){//提供公开的getXXX（）方法
             return  grass;
         }
     
         public void play(){//玩
             System.out.println("在花园的"+grass+"玩耍");
         }
     }
     
     ```

     ```java
     //1.可以通过快捷键给私有属性提供公共的getter和setter方法： alt+insert
     public class Gardon2 {
         private  String grass;
       
     	//获取值的方法
         public String getGrass() {
             return grass;
         }
     	//设置值的方法
         public void setGrass(String sendGrass) {//String grass: 局部变量
             this.grass = sendGrass;//this来区分成员变量和局部变量
         }
     }
     ```

### 8.构造方法

- 构造方法概述

  构造方法是一个方法，是一个特殊的方法，在一个类中如果具体显示提供构造方法，

  里面默认有一个无参数的构造方法。

```
比如：public  class  A{
		public A(){};//这个就是构造方法
  
  	 }	
```

  作用：创建类的对象（进行类的实例化的）和给属性赋值。

```java
  public class Gardon2 {
      private  String grass;
      //不写默认有一个无参的构造方法，当然也可以显示指定出来
      public  Gardon2(){
          System.out.println("通过无参的构造方法，创建Gardon2类的对象");
      }
      public String getGrass() {
          return grass;
      }
      public void setGrass(String sendGrass) {//String grass: 局部变量
          this.grass = sendGrass;//this来区分成员变量和局部变量
      }
      
  }

```

- 构造方法的具体使用

  作用：

  1. 通过构造方法创建类的对象

  2. 通过有参数的构造方法还可以给类的属性赋值

     ```java
     package com.it.se7.lession6;
     
     public class Gardon2 {
         private  String grass;
         //不写默认有一个无参的构造方法，当然也可以显示指定出来
         public  Gardon2(){
             System.out.println("通过无参的构造方法，创建Gardon2类的对象");
         }
         public  Gardon2(String sendGrass){//有参数的构造方法
             this.grass = sendGrass;//给类的属性赋值
             System.out.println("通过有参的构造方法，创建Gardon2类的对象");
         }
         public String getGrass() {
             return grass;
         }
         public void setGrass(String sendGrass) {//String grass: 局部变量
             this.grass = sendGrass;//this来区分成员变量和局部变量
         }
     
     }
     //测试：
     public class DemoGarDon2_Constructor {
         public static void main(String[] args) {
             //1.创建类的对象
            // Gardon2  g2  = new Gardon2();//调用的就是无参的构造方法
           //  System.out.println(g2);
             //2.创建类的对象：通过有参数的构造方法
             Gardon2 g3 = new Gardon2("小明家的草坪");
             System.out.println(g3.getGrass());
         }
     }
     
     ```

### 9.归纳总结：制作一个标准类

- 制作标准类的要求（满足封装，满足构造方法要求）
- 1. 创建一个类，提供private私有的属性
  2. 给私有的属性提供public公共的getter和setter方法
  3. 给类提供一个无参的构造方法（推荐这样使用）
  4. 给类提供对应的有参数的构造方法
  5. 给类提供一个toString()方法：打印类的所有数据

```java
package com.it.se7.lession6;

public class Student {
    //1.提供private私有的属性
    private  String name;
    private  String sex;
    private  int  age;

    public Student() {
    }

    public Student(int age) {
        this.age = age;
    }

    public Student(String name, String sex, int age) {
        this.name = name;
        this.sex = sex;
        this.age = age;
    }

    //2.public公共的getter和setter方法
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getSex() {
        return sex;
    }

    public void setSex(String sex) {
        this.sex = sex;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
    //5.提供toString（）方法

    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", sex='" + sex + '\'' +
                ", age=" + age +
                '}';
    }
}

```

















































































































































































