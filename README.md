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


Difference:  Thread is a class, so it is single-thread; while Runnable is an interface so it is multi-threaded.
