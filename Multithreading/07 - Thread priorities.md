## Thread priorities :

- Priorities are inherited from parent thread. Thus, main and child threads have same priority.

```java
public class Main extends Thread
{
    public void run(){
        System.out.println("Child Thread");
        System.out.println("Child thread priority : " + Thread.currentThread().getPriority());
    }
    
    public static void main(String[] args) {
        System.out.println("Main thread old priority : " + Thread.currentThread().getPriority());
        Thread.currentThread().setPriority(MAX_PRIORITY); // 10
        System.out.println("Main thread new priority : " + Thread.currentThread().getPriority());

        Main t = new Main();
        t.start();
    }
}
```

## Output :

```java
Main thread old priority : 5
Main thread new priority : 10
Child Thread
Child thread priority : 10
```
