# Ex.No:1(A) INTRODUCTION TO JAVA PROGRAMMING, DATA TYPES, VARIABLES AND OPERATORS

## QUESTION:
Write a program to print "Hey, my first java program!" using output statement.

## AIM:
To write a Java program that prints the message "Hey, my first java program!" to the screen.
<img width="435" height="149" alt="image" src="https://github.com/user-attachments/assets/993c2f7b-911b-495d-ac72-c2e88f951f06" />


## ALGORITHM :
1. Start the program.

2. Define a class named FirstJavaProgram.

3. Inside the class, define the main() method as the program’s entry point.

4. Use the statement System.out.println("Hey, my first java program!"); to display the message.

5. Stop the program.



## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## Sourcecode.java:

```
public class FirstJavaProgram {
    public static void main(String[] args) {
        System.out.println("Hey, my first java program!");
    }
}
```





## OUTPUT:

<img width="734" height="180" alt="image" src="https://github.com/user-attachments/assets/7e7841cb-6523-42a3-a1fe-f61739b0a7a7" />


## RESULT:
To write a Java program that prints the message "Hey, my first java program!" to the screen.



# Ex.No:1(B) CONDITIONAL STATEMENT

## QUESTION:
In a magical building, an elevator behaves oddly:

If the floor number is divisible by 3 and 5, it says "Skipped".

If the floor number is divisible by 3 only, it says "Beware!".

If the floor number is divisible by 5 only, it says "Blessings!".

Otherwise, it announces the floor number - print - "Floor {number}" .

Write a Java program to simulate this elevator logic for a given floor number.

<img width="222" height="137" alt="image" src="https://github.com/user-attachments/assets/bb41ddc8-6886-49e0-95a1-de1979d6c163" />


## AIM:
To develop a Java program that checks a given floor number and displays a special message based on its divisibility by 3 and/or 5.


## ALGORITHM :

1. Start the program and read the floor number from the user.

2. Check if the floor is divisible by both 3 and 5; if true, display "Skipped".

3. Otherwise, check if the floor is divisible only by 3; if true, display "Beware!".

4. Otherwise, check if the floor is divisible only by 5; if true, display "Blessings!".

5. If none of the above conditions are met, display "Floor {floor number}", then stop the program.





## PROGRAM:
 ```
/*
Program to implement a conditional statement using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber:  212224040330
*/
```

## SOURCE CODE:

```
import java.util.Scanner;

public class MagicalElevator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int floor = scanner.nextInt();

        if (floor % 3 == 0 && floor % 5 == 0) {
            System.out.println("Skipped");
        } else if (floor % 3 == 0) {
            System.out.println("Beware!");
        } else if (floor % 5 == 0) {
            System.out.println("Blessings!");
        } else {
            System.out.println("Floor " + floor);
        }

        scanner.close();
    }
}
```





## OUTPUT:

<img width="457" height="286" alt="image" src="https://github.com/user-attachments/assets/7ead6423-9d57-4f95-861d-bf8e646af948" />


## RESULT:
The program correctly prints “Skipped,” “Beware!,” “Blessings!,” or “Floor {number}” according to the elevator's magical rules.



# Ex.No:1(C) LOOPING STATEMENT

## QUESTION:
Write a Java program to calculate the factorial of a number using a for loop. The factorial of n is the product of all positive integers less than or equal to n.

<img width="273" height="132" alt="image" src="https://github.com/user-attachments/assets/f65cf9d3-9661-4815-88ec-90609cbf2281" />

## AIM:
To write a Java program that calculates the factorial of a given number using a for loop.


## ALGORITHM :
1. Start the program and read an integer n from the user.

2. Initialize a variable factorial to 1 to store the result.

3. Use a for loop from 1 to n, multiplying factorial by the loop counter in each iteration.

4. After the loop ends, print the value of factorial as the factorial of n.

5. Stop the program.





## PROGRAM:
 ```
/*
Program to implement a Looping Statement using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:

```
import java.util.Scanner;

public class FactorialCalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();  
        long factorial = 1;

        for (int i = 1; i <= n; i++) {
            factorial *= i;
        }

        System.out.println("Factorial of " + n + " is: " + factorial);
    }
}
```





## OUTPUT:

<img width="749" height="256" alt="image" src="https://github.com/user-attachments/assets/e75f967e-5cc0-4a71-9456-4c387a9f47d5" />


## RESULT:
The program successfully computes and displays the factorial value of the entered number.


# Ex.No:1(D) ARRAYS

## QUESTION:
Write a Java Program to Find the Average of Array Elements.

<img width="464" height="266" alt="image" src="https://github.com/user-attachments/assets/f581508f-da33-4d60-835b-63d39aca3e32" />


## AIM:
To write a Java program that calculates the average of elements in an array.


## ALGORITHM :
1. Start the program and read the number of elements n from the user.

2. Create an array of size n and read n integer elements from the user into the array.

3. Initialize a variable sum to 0 and add all array elements to sum using a loop.

4. Calculate the average by dividing sum by n and store it in a double variable.

5. Display the average value and stop the program.





## PROGRAM:
 ```
/*
Program to implement a Array concept using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:

```
import java.util.Scanner;

public class AverageArray {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = scanner.nextInt();
        }
        scanner.close();
        int sum = 0;
        for (int num : arr) {
            sum += num;
        }
        double average = (double) sum / n;
        System.out.printf("The average of elements is %.2f\n", average);
    }
}

```





## OUTPUT:

<img width="794" height="472" alt="image" src="https://github.com/user-attachments/assets/d9d45b19-9d58-49a4-a6c4-50b7c17264ec" />


## RESULT:
The program successfully computes and displays the average value of all the array elements entered by the user.



# Ex.No:1(E) STRINGS AND MATH FUNCTION

## QUESTION:
Write a Java program to reverse a given string.

<img width="325" height="118" alt="image" src="https://github.com/user-attachments/assets/16579907-d6e9-41a3-a72b-27efd0a30e28" />

## AIM: 
To write a Java program that reverses a given string entered by the user.


## ALGORITHM :
1.	Start the program and read a string input from the user.

2. Create a StringBuilder object with the input string.

3. Use the reverse() method of StringBuilder to reverse the string.

4. Convert the reversed StringBuilder back to a string.

5. Display the reversed string and stop the program.





## PROGRAM:
 ```
/*
Program to implement a Strings and Math Function using Java
Developed by: STEFFY AAVLIN RAJ F S 
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

public class ReverseString {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String str = scanner.nextLine();
        String reversed = new StringBuilder(str).reverse().toString();
        System.out.println("Reversed string: " + reversed);
        scanner.close();
    }
}
```






## OUTPUT:

<img width="729" height="257" alt="image" src="https://github.com/user-attachments/assets/83a37d9d-33db-42bb-bace-4a9af806433e" />


## RESULT:
The program successfully displays the reversed version of the input string.
