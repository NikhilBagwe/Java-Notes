## 1. Performing Single task from Single thread :

```java
class Main extends Thread
{
    // task
    public void run(){
        System.out.println("Thread task");
    }
    
    public static void main(String[] args) {
        Main t1 = new Main();  // thread 1
        t1.start();
    }
}
```

## 2. Performing Single task from Multiple threads :

- Make 1 run() method and execute it using multiple threads.
- In below example, we actually have 3 threads created - Main thread created by JVM, 2 threads created manually.

```java
class Main extends Thread
{
    // task
    public void run(){
        System.out.println("Thread task");
    }
    
    public static void main(String[] args) {
        Main t1 = new Main();  // thread 1
        t1.start();

        Main t2 = new Main();  // thread 2
        t2.start();
    }
}
```

## 3. Performing Multiple task from Single thread : Not posssible

- This case is not possible.
- A thread cannot be subdivided any further, thus it cannot handle multiple tasks.
- Eg: If in VLC we used the same thread to run multiple tasks such as playing video and music at the same time, it will play video for 1h and then will play music for 1h.

## 4. Performing Multiple task from Multiple thread :

- For every task we have to create a new class.
- Order in which threads are created dosen't define which thread is going to be executed first. It depends upon the JVM, thread scheduler and the algorithms used.
- Threads are always executed simultaneously. We can't tell which thread is created first.

```java
public class Main
{
	public static void main(String[] args) {
		MyThread1 t1 = new MyThread1();
		t1.start();  // Executes MyThread1's run() method 
		
		MyThread2 t2 = new MyThread2();
		t2.start();  // Executes MyThread2's run() method 
	}
}

// For every task we have to create a new class 
class MyThread1 extends Thread{
    public void run(){
        System.out.println("MyThread 1 task");
    }
}

class MyThread2 extends Thread{
    public void run(){
        System.out.println("MyThread 2 task");
    }
}
```
