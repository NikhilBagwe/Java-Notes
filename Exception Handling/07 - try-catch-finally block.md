# Case 1 : No exception is raised

- Catch block is never executed in this case.
```java
public class Main
{
	public static void main(String[] args) {
		try{
		    System.out.println("try");
		}
		catch(ArithmeticException e){
		    System.out.println("catch");
		}
		finally{
		    System.out.println("finally");
		}
	}
}
```
## Output :
```java
try
finally
```
# Case - 2 : Exception is raised and handled
```java
public class Main
{
	public static void main(String[] args) {
		try{
		    System.out.println("try");
		    System.out.println(10/0);
		}
		catch(ArithmeticException e){
		    System.out.println("catch");
		}
		finally{
		    System.out.println("finally");
		}
	}
}
```
## Output :

```java
try
catch
finally
```

# Case - 3 : Exception is raised but not handled
- Below code thows ArithmeticException but it is not handled.
```java
public class Main
{
	public static void main(String[] args) {
		try{
		    System.out.println("try");
		    System.out.println(10/0);
		}
		catch(NullPointerException e){
		    System.out.println("catch");
		}
		finally{
		    System.out.println("finally");
		}
	}
}
```
## Output :
```java
try
finally
Exception in thread "main" java.lang.ArithmeticException: / by zero
        at Main.main(Main.java:7)
```
