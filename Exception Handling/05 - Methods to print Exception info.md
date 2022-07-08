# Method 1 - println(e) OR println(e.toString()) :

```java
public class Main
{
	public static void main(String[] args) {
		System.out.println("Statement - 1");
		
		try{
		    System.out.println(10/0);  
		}
		catch(ArithmeticException e){
		    System.out.println(e.toString());
		    System.out.println(10/2);
		}
		
		System.out.println("Statement - 3");
	}
}
```
## Output :

```java
Statement - 1
java.lang.ArithmeticException: / by zero
5
Statement - 3
```

# Method 2 - getMessage() :

```java
public class Main
{
	public static void main(String[] args) {
		System.out.println("Statement - 1");
		
		try{
		    System.out.println(10/0);  
		}
		catch(ArithmeticException e){
		    System.out.println(e.getMessage());
		    System.out.println(10/2);
		}
		
		System.out.println("Statement - 3");
	}
}
```
## Output :

```java
Statement - 1
/ by zero
5
Statement - 3
```

# Method 3 - e.printStackTrace() :

```java
public class Main
{
	public static void main(String[] args) {
		System.out.println("Statement - 1");
		
		try{
		    System.out.println(10/0);  
		}
		catch(ArithmeticException e){
		    e.printStackTrace();
		    System.out.println(10/2);
		}
		
		System.out.println("Statement - 3");
	}
}

```

## Output :
```java
Statement - 1
java.lang.ArithmeticException: / by zero
        at Main.main(Main.java:8)
5
Statement - 3
```
