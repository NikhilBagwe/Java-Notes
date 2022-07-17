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
