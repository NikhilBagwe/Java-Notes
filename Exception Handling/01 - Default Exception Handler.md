## Example 1 :

```java
public class Main
{
	public static void main(String[] args) {
		doStuff();
	}
	
	public static void doStuff(){
	    doMoreStuff();
	}
	
	public static void doMoreStuff(){
	    System.out.println(10/0);
	}
}
```

## Output :

```java
Exception in thread "main" java.lang.ArithmeticException: / by zero
        at Main.doMoreStuff(Main.java:20)
        at Main.doStuff(Main.java:16)
        at Main.main(Main.java:12)
```

## Example 2 :

```java
public class Main
{
	public static void main(String[] args) {
		doStuff();
	}
	
	public static void doStuff(){
	    doMoreStuff();
	    System.out.println(10/0);
	}
	
	public static void doMoreStuff(){
	    System.out.println("Hello");
	}
}
```

## Output

```java
Hello
Exception in thread "main" java.lang.ArithmeticException: / by zero
        at Main.doStuff(Main.java:17)
        at Main.main(Main.java:12)
```
