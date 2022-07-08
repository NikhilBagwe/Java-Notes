# System.exit(0) :

- Only way to stop JVM from executing finally block.
- Shutdowns JVM explicitly.

```java
public class Main
{
	public static void main(String[] args) {
		try{
		    System.out.println("try");
		    System.exit(0);
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
```
