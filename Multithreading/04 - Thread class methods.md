## Print name of a thread :

```java
public class Main
{
	public static void main(String[] args) {
		System.out.println(Thread.currentThread().getName());
	}
}
```

## Changing name of main(or any) thread :

```java
public class Main
{
	public static void main(String[] args) 
	{
	    Thread.currentThread().setName("Nikhil");
	    System.out.println(Thread.currentThread().getName());
	}
}
```

## Print/change name of thread directly & isAlive() :

```java
public class Main extends Thread
{
    public void run(){
	System.out.println("Thread task");
    }
    
	public static void main(String[] args) {
	    Main t1 = new Main();
	    t1.setName("Nikhil"); 
	    t1.start();

	    // We can directly access Thread class methods using t1 inside main()
	    System.out.println(t1.getName());

	    // isAlive() might return true or false depending upon whether the thread has entered the dead state or not 
	    System.out.println(Thread.currentThread().isAlive());
	    System.out.println(t1.isAlive());
	}
}
```
