## Example - 1 :

- Code gets compiled.
- But throws ArithmeticException at runtime.

```java
public class Main
{
	public static void main(String[] args) {
		System.out.println(10/0);
	}
}
```

## Output :

```java
Exception in thread "main" java.lang.ArithmeticException: / by zero
        at Main.main(Main.java:5)
```
