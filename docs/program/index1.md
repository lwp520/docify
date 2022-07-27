# 各种模型

## IO模型

## 阻塞非阻塞模型

## 同步异步模型

## 多路转接IO模型（select）


## 概念：
阻塞和非阻塞通常被用来形容多线程间的相互影响。
解释：当一个线程占用了临界区资源，那么其它需要使用这个资源的线程都必须在这个临界区上等待。等待会导致线程挂起，这样就形成了阻塞。如果占用资源的线程一直没有释放资源，那么其它的线程在这个临界区上都不能继续工作。

相反，非阻塞表明多个线程之间的执行是不会相互影响的。 
————————————————
版权声明：本文为CSDN博主「hughjin」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/baidu_25310663/article/details/88072582



## 
阻塞调用是指调用结果返回之前，当前线程会被挂起，一直处于等待消息通知，不能够执行其他业务。函数只有在得到结果之后才会返回。

阻塞调用和同步调用不同点：
对于同步调用来说，很多时候当前线程可能还是激活的，只是从逻辑上当前函数没有返回而已，此时，这个线程可能也会处理其他的消息。
扩展：
a.如果这个线程在等待当前函数返回时，仍在执行其他消息处理，那这种情况就叫做同步非阻塞；
b.如果这个线程在等待当前函数返回时，没有执行其他消息处理，而是处于挂起等待状态，那这种情况就叫做同步阻塞；
所以同步的实现方式会有两种：同步阻塞、同步非阻塞；同理，异步也会有两种实现：异步阻塞、异步非阻塞。
————————————————
版权声明：本文为CSDN博主「hughjin」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/baidu_25310663/article/details/88072582


<font color="red">同步/异步关注的是消息通知的机制，而阻塞/非阻塞关注的是程序（线程）等待消息通知时的状态。</font>

https://blog.csdn.net/m0_38109046/article/details/89449305?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-89449305-blog-81318189.pc_relevant_multi_platform_whitelistv1&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-89449305-blog-81318189.pc_relevant_multi_platform_whitelistv1&utm_relevant_index=1