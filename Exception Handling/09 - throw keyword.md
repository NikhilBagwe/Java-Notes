# Example 1 :

```java
public class Main
{
	public static void main(String[] args) {
		throw new ArithmeticException();  // Not recommended to use predetermined exception 
	}
}
```

## Output :
```java
Exception in thread "main" java.lang.ArithmeticException
        at Main.main(Main.java:5)
```

# Example 2 : Custom Exception is thrown using 'throw' but not handled

- As we have to create an unchecked exception we are extending the custom class to RuntimeException.
- Here Default EH is printing the exception.

```java
// User-defined Exception thrown when age is less than 18
class YoungerAgeException extends RuntimeException{
    YoungerAgeException(String msg){
        super(msg);
    }
}

public class Main
{
	public static void main(String[] args) {
		int age = 16;
		
		if(age < 18){
		    throw new YoungerAgeException("You are not eligible to vote.");
		}
		else{
		    System.out.println("Voting Successful");
		}
	}
}
```

## Output :
```java
Exception in thread "main" YoungerAgeException: You are not eligible to vote.
        at Main.main(Main.java:14)
```

# Example 3 : Custom exception thrown and handled

```java
import java.util.Scanner;

class YoungerAgeException extends RuntimeException{
    YoungerAgeException(String msg){
        super(msg);
    }
}

public class Main
{
	public static void main(String[] args) {
	    Scanner s = new Scanner(System.in);
	    System.out.println("Enter your age : ");
	    
		int age = s.nextInt();
		
		try{
		    if(age < 18){
		        throw new YoungerAgeException("You are not eligible to vote.");
    		}
    		else{
    		    System.out.println("Voting Successful");
    		}
		}
		catch(YoungerAgeException e){
		    e.printStackTrace();
		}
		
		System.out.println("Program completely executed!!");
	}
}
```

## Output :
```java
Enter your age : 
16
YoungerAgeException: You are not eligible to vote.
        at Main.main(Main.java:20)
Program completely executed!!
```
