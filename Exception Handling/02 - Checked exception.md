## Example 1 :

- In below example, FileNotFoundException didn't occur, but the compiler is warning us that it may happen at runtime.
- Compiler tells that the above exception is not handled.

```java
import java.io.*;

public class Main
{
	public static void main(String[] args) {
		PrintWriter pw = new PrintWriter("abc.txt");
		pw.println("Hello");
	}
}

```
## Output :

```java
error: unreported exception FileNotFoundException; must be caught or declared to be thrown
		PrintWriter pw = new PrintWriter("abc.txt");
```
