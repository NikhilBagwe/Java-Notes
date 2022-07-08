# Example 1 :

- Always write catch blocks from Child class to Parent class.
- Below code will give error as the Exception is getting caught twice.

```java
public class Main
{
	public static void main(String[] args) {
		try{
		    System.out.println(10/0);
		}
		catch(Exception e){
		    System.out.println("Exception - Parent class");
		}
		catch(ArithmeticException e){
		    System.out.println("ArithmeticException - Child class of Exception");
		}
	}
}
```
## Output :

```java
Main.java:11: error: exception ArithmeticException has already been caught
		catch(ArithmeticException e){
```

# Corrected code :
```java
public class Main
{
	public static void main(String[] args) {
		try{
		    System.out.println(10/0);
		}
		catch(ArithmeticException e){
		    System.out.println("ArithmeticException - Child class of Exception");
		}
		catch(Exception e){
		    System.out.println("Exception - Parent class");
		}
	}
}
```
## Output :
```java
ArithmeticException - Child class of Exception
```
