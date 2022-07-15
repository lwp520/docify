## static和final
static：静态的，全局的
static可以修饰：变量，方法，代码段，内部类，独属于属于类
静态变量（类变量），静态方法，静态代码块在类加载子系统（classload）过程中就完成了，内部类应该也是这个时候，不太清楚现在，

final：最终的，不可修改
final可以修饰：：属性，方法，类，局部变量
final修饰的属性的初始化可以在编译期，也可以在运行期，初始化后不能被改变。

普通的成员变量则是在实例化对象时进行初始化的


## public，default，private，protected
**修饰符:**
    <font color=Blue>权限修饰符</font>: private, default, protected, public
    <font color=Blue>状态修饰符</font>: static, final
    <font color=Blue>抽象修饰符</font>: abstract

1. **类:**
    <font color=Blue>权限修饰符</font>:default，public
    default：就是同一包下（本身就不用import）可以访问，但是在不同包下不可以访问（就是你创建了一个这个类的实例并且import包编译会报错，并且提示你设为public）
    <font color=Blue>状态修饰符</font>:final
    表示该类不可以被继承，不可以进行扩展
    <font color=Blue>抽象修饰符</font>:abstract
    表示该类不可以被实例化，当然当你对具体的子类实例化时会对父类实例化，放在子类可以访问的空间里
    用的最多的就是：public

2. **成员变量：**
    <font color=Blue>权限修饰符</font>:private，default，protected，public
    前提是外部有一个类有权限可以访问到这个类，
    然后再根据成员变量的修饰符判断这个类符不符合修饰符所在的位置
    状态修饰符：static，final
    用的最多的就是：private

3. **构造方法：**
    权限修饰符：private，default，protected，public
    用的最多的就是：public

4. **成员方法：**
    权限修饰符：private，default，protected，public
    状态修饰符：static，final
    抽象修饰符：abstract
    用的最多的就是：public

5. **除此以外的组合规则：**
    成员变量：public static final
    成员方法：
        public static
        public abstract
        public final

在面向对象中, 三大特性(封装, 继承, 多态)的理解尤为重要, 但同时理解这四种权限修饰关系, 对于谁能调用谁, 是否有访问权限等问题, 解决起来更得心应手!


