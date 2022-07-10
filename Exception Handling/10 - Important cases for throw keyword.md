## Case 1 : 'e' refers to 'null' resulting into NullPointerException

1. 'e' is assigned properly by creating obj of ArithmeticException class, thus it refers to ArithmeticException.
```java
public class Main
{
    static ArithmeticException e = new ArithmeticException();
    
	public static void main(String[] args) {
		throw e;
	}
}
```

## Output
```java
Exception in thread "main" java.lang.ArithmeticException
        at Main.<clinit>(Main.java:4)
```

2. Object of AE is not created, thus 'e' points to null giving NullPointerException
```java
public class Main
{
    static ArithmeticException e;
    
	public static void main(String[] args) {
		throw e;
	}
}
```

## Output
```java
Exception in thread "main" java.lang.NullPointerException
        at Main.main(Main.java:7)
```

## Case 2 : Unreachable statement
- If the compiler knows that an exception is going to be raised beforehand, then the code after 'throw' becomes unreachable for it.
- Thus we get an compile time error.

```java
public class Main
{
	public static void main(String[] args) {
		throw new ArithmeticException("/ by zero");
		System.out.println("Hello");
	}
}
```
## Output :
```java
Main.java:6: error: unreachable statement
		System.out.println("Hello");
		^
1 error
```
```java
```
```java
```
