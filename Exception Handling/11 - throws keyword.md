## Unreported exception :

- As we are not handling the checked exception i.e InterruptedException, we get compile time error.
- When the main thread goes into sleep, it may be interrupted by other threads. Thus, InterruptedException is raised.

```java
public class Main
{
	public static void main(String[] args) {
	    Thread.sleep(1000);
		System.out.println("Hello World");
	}
}
```
## Output :
```java
Main.java:5: error: unreported exception InterruptedException; must be caught or declared to be thrown
	    Thread.sleep(1000);
	                ^
1 error
```
## There are two ways to handle above code :
1. Try-catch
2. throws keyword

## Method 1 : try-catch : Recommended approach
- After 1 sec, 'Hello World' is printed.
- This method is recommended as it is responsibility of the method in which exception is raised to handle it, instead of delegating it like we do using 'throws'.
```java
public class Main
{
	public static void main(String[] args) {
	    try{
	        Thread.sleep(1000);
	    }
	    catch(InterruptedException e){
	        
	    }
		System.out.println("Hello World");
	}
}
```
## O/p :
```java
Hello World
```

## Method 2 - throws keyword

```java
public class Main
{
	public static void main(String[] args) throws InterruptedException
	{
	    Thread.sleep(1000);
		System.out.println("Hello World");
	}
}
```
## O/p :

```java
Hello World
```
