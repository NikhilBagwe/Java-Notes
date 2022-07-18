## interrupt() :

- Thread must be in sleeping/waiting state.
- sleep() or wait() method must be used on thread, to see effect of interrupt() method.

```java
public class Main extends Thread
{
    public void run(){
        try{
            for(int i=1; i<=5; i++){
                System.out.println("child thread : " + i);
                
                // When thread goes into sleeping state, it gets interrupted and thus goes into catch block and prints exception
                Thread.sleep(1000); 
            }
        }
        catch(InterruptedException e){
            System.out.println(e);
        }
    }
    
    public static void main(String[] args) {
      Main t = new Main();
      t.start();

      t.interrupt();
    }
}
```

```java
child thread : 1
java.lang.InterruptedException: sleep interrupted
```
