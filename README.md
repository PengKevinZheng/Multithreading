# Multithreading

Two methods to create a new thread:

1. class Mythread extends Thread{
   ...
   @Overriding
   public void run(){
   ...
   }
   
  }
  Mythread mt = new Mythread();
  mt.start();
  
2.class Mythread implements Runnable{
...
@Override
public void run(){
..
}
}
Mythread mt = new Mythread();
Thread t = new Thread(mt);
t.start();


Difference:  1. Thread is a class, so it is single-thread; while Runnable is an interface so it is multi-threaded.
            2. Runnable is good at dealing with shared data. because: MyRunnable mr = new MyRunnable(); Thread t1 = new Thread(); Thread t2 = new Thread();  Then these two thread both belong to the mr object.
            
            
How to avoid dead lock:
大部分代码并不容易产生死锁，死锁可能在代码中隐藏相当长的时间，等待不常见的条件地发生，但即使是很小的概率，一旦发生，便可能造成毁灭性的破坏。避免死锁是一件困难的事，遵循以下原则有助于规避死锁： 

     1、只在必要的最短时间内持有锁，考虑使用同步语句块代替整个同步方法；

     2、尽量编写不在同一时刻需要持有多个锁的代码，如果不可避免，则确保线程持有第二个锁的时间尽量短暂；

     3、创建和使用一个大锁来代替若干小锁，并把这个锁用于互斥，而不是用作单个对象的对象级别锁；
