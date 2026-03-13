# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:
Create a Super class Person with fields name and age. Create a subclass Student that inherits from Person and adds a field marks (integer). Implement a method in Student called calculateGrade() which returns the grade based on the marks:

Marks ≥ 90: Grade A

Marks ≥ 75 and < 90: Grade B

Marks ≥ 50 and < 75: Grade C

Marks < 50: Grade F


## AIM:
Create a Person superclass and a Student subclass with a marks field, and calculate the grade based on marks.


## ALGORITHM :
1. Start and import Scanner to read user input.

2. Create a superclass Person with fields name and age, and a subclass Student that    adds a marks field.

3. Read the student’s name, age, and marks from the user.

4. Create a Student object and call the calculateGrade() method to determine the       grade based on marks.

5. Display the student’s name, age, marks, and grade, then end the program.





## PROGRAM:
 ```
/*
Program to implement a Inheritance and Aggregation using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:

```
import java.util.Scanner;


class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}


class Student extends Person {
    int marks;

    Student(String name, int age, int marks) {
        super(name, age); 
        this.marks = marks;
    }

    String calculateGrade() {
        if (marks >= 90)
            return "A";
        else if (marks >= 75)
            return "B";
        else if (marks >= 50)
            return "C";
        else
            return "F";
    }
}


public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

       
        String name = sc.nextLine();

        
        int age = sc.nextInt();

       
        int marks = sc.nextInt();

        Student s = new Student(name, age, marks);

       
        System.out.println("Name: " + s.name);
        System.out.println("Age: " + s.age);
        System.out.println("Marks: " + s.marks);
        System.out.println("Grade: " + s.calculateGrade());

        sc.close();
    }
}
```





## OUTPUT:

<img width="499" height="558" alt="image" src="https://github.com/user-attachments/assets/c2496d4c-ee9d-4acd-8869-4320d63a64cb" />



## RESULT:
The program displays the student’s name, age, marks, and corresponding grade.

