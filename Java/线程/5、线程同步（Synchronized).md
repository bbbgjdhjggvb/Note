保证数据在任何同一时刻，只能有一个线程访问
1. 同步代码块
```
Synchronized(object){
	//需要同步的代码块
}
```
2. 同步方法：Synchronized放在方法声明中，表示整一个方法同步
```
public Synchronized void foo;
```
#### 互斥锁
1. 每一个对象都有一个互斥锁的标记，该标记保证每次只有一个线程可以访问被标记过的对象
2. 当一个对象被synchronized修饰时表示只有一个线程可以访问该对象
	1. 非静态锁，锁是this或者其他对象，非静态方法的锁，非静态方法中的同步代码块
3. 静态锁，锁是类.class，静态方法的锁，静态方法中的同步代码块

#### 释放锁
1. 同步代码块、方法结束
2. 同步代码块、方法中遇到break和return
3. 同步代码块、方法中出现为处理的error
4. ～执行线程对象的wait()方法
#### 不释放锁
1. 调用sleep，yeild方法暂停当前线程的执行，不会释放锁
2. 