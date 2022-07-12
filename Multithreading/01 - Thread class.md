## Creating thread using Thread class :
 
```java
// 1. Extends to 'Thread'
public class Main extends Thread
{
    // 2. Override run()
    public void run(){
        System.out.println("Thread task");
    }
    
	public static void main(String[] args) {
                // 3. Create an obj
		Main t = new Main();
    		// 4. Start thread using start()
		t.start();
	}
}
```
