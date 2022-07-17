## join() :

- join() method is called on main thread.
- In below code, the Main thread will wait for child thread to complete its execution and then continue its own execution.

```java
public class Main extends Thread
{
    public void run(){
        try{
            for(int i = 1; i<=5; i++){
                System.out.println("child thread : " + i);
                Thread.sleep(1000);
            }
        }
        catch(Exception e){
            System.out.println(e);
        }
    }
    
    public static void main(String[] args) throws InterruptedException
    {
        Main t1 = new Main();
        t1.start();

        t1.join();  // main thread will stop here and let child thread complete its execution

        try{
            for(int i = 1; i<=5; i++){
                System.out.println("main thread : " + i);
                Thread.sleep(1000);
            }
        }
        catch(Exception e){
            System.out.println(e);
        }
    }
}

```

## Output :

```java
child thread : 1
child thread : 2
child thread : 3
child thread : 4
child thread : 5
main thread : 1
main thread : 2
main thread : 3
main thread : 4
main thread : 5
```
