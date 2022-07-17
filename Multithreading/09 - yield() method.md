## yield() :

- Stops execution of current thread and executes other waiting thread of same priority.
- In below example, if thread scheduler accepts hint then Main thread stops executing and Thread-0 (or any other thread) is executed.
- Output varies everytime.

```java
public class Main extends Thread
{
    public void run(){
        for(int i = 1; i <= 5; i++){
            System.out.println(i + " : " + Thread.currentThread().getName());
		}
    }
    
	public static void main(String[] args) 
    {
		Main t1 = new Main();
		t1.start();
		
		Thread.yield();  // thread scheduler might accept or ignore this hint, thus o/p varies everytime
		
		for(int i = 1; i <= 5; i++){
            System.out.println(i + " : " + Thread.currentThread().getName());
		}
	}
}
```

## Output - Differs everytime - Below o/p is desired one for above example

```java
1 : Thread-0
2 : Thread-0
3 : Thread-0
4 : Thread-0
5 : Thread-0
1 : main
2 : main
3 : main
4 : main
5 : main
```
