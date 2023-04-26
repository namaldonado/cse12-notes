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

### 3.8
```
import java.util.Scanner;

public class Exercise03_08 {
    public static void main(String[] args) {

        System.out.println("Please enter a three integers:");
        Scanner input = new Scanner(System.in);
	
	// reads three integer using the nextInt() method of the Scanner object and stores them in 
	// variables x, y, and z
        int x = input.nextInt();
        int y = input.nextInt();
        int z = input.nextInt();
	
        if (x > y) { 
	    // compares x and y, if x > y, values of v and y are swapped using a temporary
	    // variable temp1
            int temp1 = x;
            x = y;
            y = temp1;
        }
	
	// compares y and z, and if y > z, values are swapped, etc.
        if (y > z) {
            int temp2 = y;
            y = z;
            z = temp2;
        }
	
	// compares x and y AGAIN, if x > y, values are swapped using temporary variable temp3. necessary
	// because if first 2 statements might have changed the value of x and y
        if (x > y) {
            int temp3 = x;
            x = y;
            y = temp3;
        }
        System.out.println(x + "" + y + "" + z);

    }
}
```

### 3.14 Write a program that lets the user guess whether the flip of a coin results in heads or tails. The program randomly generates and integer 0 or 1, which represents head or tail. The program prompts the user to enter a guess and reports whether the guess is correct or incorrect 

```
import java.util.Scanner; 
public class Exercise03_14 {
	public static void main(String[] args) {
		int x = (int) (Math.random() * 2); // makes sure you're generating 2 numbers 
		System.out.println("Enter your guess now! 0 for heads, or 1 for tails:");
		Scanner input = new Scanner(System.in);
		int a = input.nextInt();
		if (a == x) {
			System.out.println("You are correct!");
		} else {
			System.out.println("Wrong! Better luck next time!");
			System.out.println("The correct anwser was: " + x);
		}
		input.close();
	}
}
```

### 3.23 Write a program that prompts the user to enter a point (x, y) and checks whether the point is within the rectangle centered at (0,0) with width 10 and height 5.
<p>
	For example, (2,2) is inside the rectangle and (6,4) is outside the rectangle
	
```
import java.util.Scanner; 
public class Exercise03_23 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("\nEnter a point with two coordinates: ");
        double x2 = in.nextInt();
        double y2 = in.nextInt();
        double x1 = 0;
        double y1 = 0;
        double rectWidth = 10;
        double rectHeight = 5;
        String res = "";
        if (x2 <= 10.0 / 2 && y2 <= 5.0 / 2) {
            res += "is in the rectangle";
        } else {
            res += "is not in the rectangle";
        }
        System.out.println("Point (" + x2 + ", " + y2 + ") " + res + " Centered at (0,0) with a Height of 5 and " +
                "a Width of 10");

        in.close();
    }
}
```
### 4.13 Write a program that prompts the user to enter a letter
	check whether the letter is a vowel or a constant

```
import java.util.*;

public class Exercise04_13 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.println("Enter a letter: ");
        String str = in.next().trim();
        if (str.length() > 1) {
            System.out.println(str + " is invalid input.");
        } else {
            char ch = str.charAt(0);
            if (Character.isLetter(ch)) {
                String s = ch + "";
                String res = "";
                if ("aeiou".contains(s.toLowerCase())) {
                    res += "vowel";
                } else {
                    res += "consonant";
                }

                System.out.println(ch + " is a " + res);

            } else {
                System.out.println(ch + " is invalid input.");
            }
        }
        in.close();
    }
}
```
	
### 4.20 Write a program that prompts the user to enter a string and displays its length and its first character
```
import java.util.*;

public class Exercise04_20 {
     public static void main(String[] args) {
         Scanner in = new Scanner(System.in);
         System.out.println("Enter a string: ");
         String s = in.next();
         System.out.println("Length is " + s.length() + " First char is " + s.charAt(0) );


    }
}
```
	
### 4.22 Write a program that prompts the user to enter two strings and reports whether the second string is a substring of the first string.
	Example: s1=ABCD, s2=BC, BC is a substring ABCD

```
import java.util.Scanner;
	
public class Exercise04_22 {
    public static void main(String[] args) {

        Scanner in = new Scanner(System.in);
        System.out.print("Enter string s1: ");

        String s1 = in.next();
        System.out.print("Enter string s2: ");
        String s2 = in.next();

        int longestLength = Math.max(s1.length(), s2.length());
        final String IS_A = " is a";
        final String IS_NOT = " is not a";
        String big, small;

        if (longestLength == s1.length()) {
            big = s1;
            small = s2;

        } else {
            big = s2;
            small = s1;
        }
        String result = "";
        if (big.contains(small)) {
            result += IS_A;
        } else {
            result += IS_NOT;
        }


        System.out.print(small + result + " substring " + big);
        in.close();
    }
}
```
	
	
### 4.24 Write a program that prompts the user to enter three cities and displays them in ascending order
```
import java.util.Scanner;
	
public class Exercise04_24 {
    public static void main(String[] args) {
        String tempCity = "";
        Scanner input = new Scanner(System.in);
        System.out.print("Enter the name of city 1: ");
        String cityOne = input.next();
        System.out.print("Enter the name of city 2: ");
        String cityTwo = input.next();
        System.out.print("Enter the name of city 3: ");
        String cityThree = input.next();
        if (cityOne.charAt(0) > cityTwo.charAt(0)) {
            tempCity = cityTwo;
            cityTwo = cityOne;
            cityOne = tempCity;

            if (cityTwo.charAt(0) > cityThree.charAt(0)) {
                tempCity = cityThree;
                cityThree = cityTwo;
                cityTwo = tempCity;
            }
        }
        System.out.println("The cities in alphabetical order are: "
                + cityOne + " " + cityTwo + " " + cityThree + ".");
    }
}
```
	
### 5.50 Write a program that prompts the user to enter a string and displays the number of the upper-case letters in the string. 

```
import java.util.Scanner;

public class Exercise05_50 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Enter a string with some uppercase letters: ");
        String toBeevaluated = input.nextLine();
        int numberOfuppercase = 0;
        int x = 0;
        while (x < toBeevaluated.length()) {

            if (Character.isUpperCase(toBeevaluated.charAt(x))) {
                numberOfuppercase++;
            }
            x++;
        }
        System.out.println("The number of upper case letters is: " + numberOfuppercase);
    }
}	
```

### 6.6 Write a method to display a pattern as follows:
1
2 1
3 2 1
...
```
import java.util.*;

public class Exercise06_06 {
    public static void displayPattern(int n) {
        int pad = n - 1; //Track padding to loop for each line
        for (int r = 1; r <= n; r++) { //Main loop
            for (int p = 0; p < pad; p++) {
                System.out.print("  ");
            }
            for (int i = r; i > 0; i--) {
                System.out.print(i + " ");
            }
            System.out.println();
            pad--; // decrease padding as we increase r in for loop
        }
    }
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Enter the number of rows to print: ");
        int userRows = input.nextInt();
        displayPattern(userRows);
    }
}
```
					  
### 6.18 Some websites impose certain rules for passwords. Write a method that checks whether a string is a valid password. Suppose the password rules are as follows:
- A password must have at least eight characters
- A password consists of only letters and digits 
- A password must contain at least two digits 
Write a program that prompts the user to enter a password and displays valid password if the rules are followed or invalid password otherwise 
```
import java.util.Scanner;
	
public class Exercise06_18 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.println("Enter the password to check: ");
        String pwd = in.next();
        System.out.println(validatePassword(pwd) ? "Valid Password" : "Invalid Password");
        in.close();
    }
    static boolean validatePassword(String pword) {
        int countDigits = 0;
        if (pword.length() < 8) {
            return false;
        }
        for (int i = 0; i < pword.length(); i++) {
            char c = pword.charAt(i);
            if (Character.isDigit(c)) {
                countDigits++;
            } else if (!Character.isLetter(c)) {
                return false; // Not a digit or a letter
            }
        }
        return countDigits >= 2;
    }
}
```
					  
### 6.20 Write a method that counts the number of letters in a string. Write a test program that prompts the user to enter a string and displays the number of letters in the string. 
```
import java.util.Scanner;
	
public class Exercise06_20 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.println("Enter a string:");
        String s = in.next();
        System.out.println("Number of letters: " + countLetters(s));
        in.close();
    }
    public static int countLetters(String s) {
        int count = 0;
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if (Character.isLetter(c)) {
                count++;
            }
        }
        return count;
    }
}
```
				       
### 6.30 Roll two dice. Each die has six faces representing values 1, 2, …, and 6, respectively. Check the sum of the two dice. If the sum is 2, 3, or 12 (called craps), you lose; if the sum is 7 or 11 (called natural), you win; if the sum is another value a point is established. Continue to roll the dice until either a 7 or the same point value is rolled. If 7 is rolled, you lose. Otherwise, you win. Your program acts as a single player. Here are some sample runs.
