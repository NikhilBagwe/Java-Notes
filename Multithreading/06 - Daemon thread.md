## Create Daemon thread :

- Create/Convert the thread to Daemon thread before starting it.

```java
public class Main extends Thread
{
    public void run(){
        if(Thread.currentThread().isDaemon()){
            System.out.println("Daemon Thread");
        }
        else{
            System.out.println("Child Thread");
        }
    }
    
    public static void main(String[] args) {
        System.out.println("Main Thread");

        Main t = new Main();
        t.setDaemon(true);  // Converting the thread to Daemon thread
        t.start();
    }
}
```
