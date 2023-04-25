# CSE 12 Notes 
## Java Introduction

### 1.1 Write a program that displays Welcome to Java, 

```
public class Exercise01_01 {    
// defines a public class called "Exercise01_01"

  public static void main (String[] args) {   
  // public main method called "main"
  // takes an array of strings as an argument named "args"
  
    System.out.println("Welcome to Java");    
    //calls the "println" method of the "System" class
    // passing the string literal "Welcome to Java" 
  }
}

```

### 1.2 Write a program that displays Welcome to Java 5 times

```
public class Exercise01_02 {
// public class named "Exercise01_02"

    public static void main(String[] args) {
    // public statis method names "main"
    
        int count = 0;  // variable int, initialized to 0
        while (count < 5) {    // while loop used to repeat a block of code until a condition is met
            System.out.print("Welcome to Java\n");
            count++;  // count incremented by 1
        }
    }
}

```

### 1.5 Write a program that Computes basic expressions

```
public class Exercise01_05 {
    public static void main(String[] args) {
        
        // code initializes two double variables "numerator" and "denominator"
        double numerator = (9.5 * 4.5) - (2.5 * 3);  // output: 21.25
        double denominator = 45.5 - 3.5; // output: 42.0

        double solution = numerator / denominator;  // calculates the division of numerator by denominator

        String outStr = solution + " ";  // concatenates the value of "solution" with a space character

        System.out.printf("%.4f", solution); // prints out value of 'solution' to console 
        // with 4 decimal places using format specifier: '"%.4f"'
        
        // output: 0.6234
    }
}

```

### 1.9 Write a program that displays the area and perimeter of a rectangle with the width of 4.5 and height of 7.9 using the formula: A = W x H

```
public class Exercise01_09 {
    public static void main(String[] args) {

        double area = 4.5 * 7.9;
        area = Math.round(area * 100);  // Math.round method to round the value of 'area' to 2 deci places
        area /= 100;

        System.out.println("The area of a rectangle with a width of 4.5 and a height"
                + " of 7.9 is " + area);
        
        System.out.println("Perimeter is " + (2 * (4.5 + 7.9)));
    }
}

```
### 2.1 Write a program that reads Celsius in double value from the console and converts it to farenheit
```
import java.util.Scanner;   // imports 'Scanner' class from the java.util pacakage

public class Exercise02_01 {
	public static void main(String[]args) { 
    // declares two variables: 'Celsius' and 'Fahrenheit'
		double Celsius; 
		double Fahrenheit;
		
		System.out.println("Enter degrees in Celsius");
		Scanner input = new Scanner(System.in); // 'Scanner' object named 'input' reads input from console
		Celsius = input.nextDouble();
		
		Fahrenheit = (9.0/5.0 * Celsius + 32);

		System.out.println(Fahrenheit);
		
		input.close();  // close() method of Scanner object 'input' to release any resources associated w/ it 
	}
}

```

### 2.6 Write a program that reads an interger between 0 and 1000 and adds all digits in the integer. For example, if an integer is 932, the sum of all digits is 14.

```
import java.util.Scanner;

public class Exercise02_06 {
    // main method prompt user to enter an integer
    public static void main(String[] args) {
        System.out.print("Enter an integer to discover the sum of its digits: ");
        
        // reads the input from the user by creating a new 'Scanner' object named 'input' that
        // reads input from the console using the 'System.in' stream
        Scanner input = new Scanner(System.in);
        
        // integer entered is assigned to the variable 'userNumber'
        int userNumber = input.nextInt();
        
        // main method calls the 'sumDigits' method and passes 'userNumber' as an argument
        System.out.println(sumDigits(userNumber));
    }
    
    // takes an integer argument 'a' and calculates the sum of the digits of an interger 
    // by using a while loop. 
    private static int sumDigits(int a) {
        int sum = 0;
        while (a > 0) {
            
            // Inside the loop, the remainder of 'a' divided by 10 is added to 
            // the 'sum' variable, which keeps track of the running total of the digits. 
            sum += (a % 10);
            
            // 'a' is divided by 10 to remove the last digit from 'a' and continue the loop
            // until all digits have been added to 'sum'
            a /= 10;
        }
        return sum;
    }
}

```

### 2.15 Write a program that prompts the user to enter two points (x1, y1) and (x2, y2) and displays their distance between them. The formula for computing the distance is sqrt[(x2 - x1)^2 + (y2 - y1)^2].

```
import java.util.Scanner;

public class Exercise02_15 {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Enter x1 and y1: ");
        double x1, x2, y1, y2;
        x1 = input.nextDouble();
        y1 = input.nextDouble();
        System.out.println("Enter x2 and y2: ");
        x2 = input.nextDouble();
        y2 = input.nextDouble();

        // Math.pow == square 
        double exs = Math.pow((x2 - x1), 2);
        double whys = Math.pow((y2 - y1), 2);
        --------------------------------------------------------
        double a = Math.pow((exs + whys), 0.5);
        System.out.println("The distance between the two points is " + a);


    }

}
```


