## Thread.sleep() :

- It is a static method that throws InterruptedException at compile time, thus need to be handled using try-catch or 'throws'.
- In below example, numbers 1 to 5 will be printed with a delay of 1sec.
- Main thread execution is paused for 1sec.

```java
public class Main
{
	public static void main(String[] args) 
	{
		for(int i = 1; i <= 5; i++){
		    try{
		        Thread.sleep(1000);  // Main thread goes into sleep for 1sec
		        System.out.println(i);
		    }
		    
		    catch(InterruptedException e){
		        System.out.println(e);
		    }
		}
	}
}
```

## Example :

- In below example, both threads t1, t2 are executed simultaneously as we are using start().
- Thus, here we can see the concept of multithreading.
- If we directly used run() method the o/p will be different. First 1-5 for t1 object will be printed by main thread and then 1-5 for t2 obj. In this case threads are never formed.

```java
public class Main extends Thread
{
    public void run(){
        for(int i = 1; i <= 5; i++){
		    try{
		        System.out.println(i + " : " + Thread.currentThread().getName());
		        Thread.sleep(1000);
		    }
		    
		    catch(InterruptedException e){
		        System.out.println(e);
		    }
		}
    }
    
	public static void main(String[] args) 
	{
	    //Both threads t1, t2 are executed simultaneously
		Main t1 = new Main();
		t1.start();

		Main t2 = new Main();
		t2.start();
	}
}

```
