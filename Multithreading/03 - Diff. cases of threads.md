## Performing Single task from Single thread :

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

## Performing Single task from Multiple threads :

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

## Performing Multiple task from Single thread : Not posssible

- This case is not possible.
- A thread cannot be subdivided any further, thus it cannot handle multiple tasks.
- Eg: If in VLC we used the same thread to run multiple tasks such as playing video and music at the same time, it will play video for 1h and then will play music for 1h.
