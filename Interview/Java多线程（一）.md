# Java多线程（一）--------Java线程基础
### 什么是线程？什么是进程？
进程是具有一定独立功能的程序关于某个数据集合上的一次运行活动,是系统进行资源分配和调度的一个独立单位，在“window任务管理器”中，我们完全可以将运行在内存中的exe文件看成进程。

线程可以理解为在进程中独立运行的子任务。比如QQ.exe运行时就可以有很多子任务同时运行，传输文件线程、发送消息线程等，这些不同的任务或者说功能都可以同时运行，其中每项任务都可以理解为一个线程在工作。
### 线程跟进程有啥区别？为什么要使用多线程？
线程和进程最主要的区别在于他们操作系统的资源管理方式。进程有独立的地址空间，一个进程崩溃后，在保护模式下对不会对其他进程产生影响。而线程是进程中的不同执行任务，线程有自己的堆栈和局部变量，但是没有独立的地址空间，一个线程死掉就相当于整个进程死掉。

1. 一个程序至少有一个进程，一个进程至少有一个线程。
2.  线程的划分尺度小于进程，一个线程可以创建和撤销另一个线程;同一个进程中的多个线程之间可以并发执行。
3. 进程在执行过程中拥有独立的内存单元，而多个线程共享内存，从而极大地提高了程序的运行效率。
4. 每个独立的线程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。

对于一些要求同时进行并且又要共享某些变量的并发操作，只能用线程，不能用进程。在进程内创建、终止线程比创建、终止进程要快；同一进程内的线程间切换比进程间的切换要快,尤其是用户级线程间的切换。

## 线程的实现
学习如何创建线程前，先看下Thread类的结构，如下：

public class Thread implements Runnable

从上面的源码可以看出，Thread类实现了Runnable接口，它们之间具有多态性。使用继承Thread类的方式创建新线程时，最大的局限就是不支持多继承，Java语言的特点是单根继承，所以为了支持多继承，完全可以实现Runnable接口的方式，一边实现一边继承。但使用两种方式创建的线程在工作时的性质是一致的，没有本质的区别。
1. 继承Thread

创建一个自定义线程MyThread.java,此类继承Thread,并重新run方法，在run方法中，写线程要执行的代码：

    public class MyThread extends Thread{
    	@override
    	public void run(){
    		super.run;
    		System.out.println("MyThread");
    	}
    }

2. 实现Runnable接口
继续创建创建一个实现Runnable接口的类MyRunnable,代码如下：
``` java
public class MyRunnable implements Runnable{
	@override
	public void run (){
		System.out.println("aaaa");
	}
}

public class Run{
	public staic void main(String[] args){
		Runnable runnable = new MyRunnable();
		Thread thread = new Thread(runnable);
		thread.start();
		System.out.println("bb");
		
	}
}
```

