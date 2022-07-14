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
