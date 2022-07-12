## Creating thread using Runnable interface :

```java
// 1. Implments to Runnable interface
public class Main implements Runnable
{
    // 2. Override run()
    public void run(){
        System.out.println("Thread task");
    }
    
    public static void main(String[] args) {
      // 3. Create an obj 
      Main t = new Main();
      // 4. Create an obj of Thread class and pass obj created in 3rd step as parameter
      Thread th = new Thread(t);
      // 5. Start the thread 
      th.start();
    }
}
```
