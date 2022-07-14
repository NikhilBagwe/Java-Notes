## Example :

- Here when pgm starts execution, JVM first creates the main thread.
- Main thread executes -> the main() method.
- While executing main(), main thread creates another thread - Thread-0 as per pgm instructions.
- Then, Thread-0 executes -> run().
- So here, diff. methods are executed by diff. threads.

```java
public class Main extends Thread
{
    public void run(){
        System.out.println("Thread task");
        System.out.println("Thread executing run() :" + Thread.currentThread().getName());
    }
    public static void main(String[] args) 
    {
        Main t1 = new Main();
        t1.start();
        System.out.println("Thread executing main() :" + Thread.currentThread().getName());
    }
}
```
## Output :

```java
Thread task
Thread executing run() :Thread-0
Thread executing main() :main
```
