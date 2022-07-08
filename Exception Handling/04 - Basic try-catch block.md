## Code throws exception leading to abnormal termination :

```java
public class Main
{
	public static void main(String[] args) {
		System.out.println("Statement - 1");
		
		System.out.println(10/0);  // Risky Code
		
		System.out.println("Statement - 3");
	}
}
```
## Output :

```java
Statement - 1
Exception in thread "main" java.lang.ArithmeticException: / by zero
        at Main.main(Main.java:8)
```

## Performing Exception Handling :

- Keeping risky code inside try block.
- Provides graceful termination.

```java
public class Main
{
	public static void main(String[] args) {
		System.out.println("Statement - 1");
		
		try{
		    System.out.println(10/0);  // Risky Code
		}
		catch(ArithmeticException e){
		    System.out.println(10/2);
		}
		
		System.out.println("Statement - 3");
	}
}
```

## Output :

```java
Statement - 1
5
Statement - 3
```
