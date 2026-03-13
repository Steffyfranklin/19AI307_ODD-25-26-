# Ex.No:2(A) CLASS AND OBJECT

## QUESTION:
Create a class Car with attributes brand, model, year. Create 2 objects and print their details.

<img width="292" height="173" alt="image" src="https://github.com/user-attachments/assets/957fc6a4-0cef-495d-b138-f59c191c5c89" />



## AIM:
To create a Java class Car with attributes brand, model, and year, and display the details of two car objects.


## ALGORITHM :
1.	Start the program and define a class Car with attributes brand, model, and year.

2. Create a constructor in the Car class to initialize the attributes.

3. Define a display method in the Car class to print the car details with a label.

4. In the main method, create two Car objects with different attribute values.

5. Call the display method for each object to print their details and stop the          program.





## PROGRAM:
 ```
/*
Program to implement a Class and Objects using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
class Car {
    String brand;
    String model;
    int year;

    Car(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    public void display(String label) {
        System.out.println(label + ": " + brand + " " + model + " " + year);
    }
}

public class CarDemo {
    public static void main(String[] args) {

        Car car1 = new Car("Toyota", "Innova", 2022);
        Car car2 = new Car("Hyundai", "i20", 2021);

        car1.display("Car 1");
        car2.display("Car 2");
    }
}
```






## OUTPUT:

<img width="695" height="186" alt="image" src="https://github.com/user-attachments/assets/db44eda4-4363-45b4-9881-5a444b2f20e2" />


## RESULT:
The program successfully creates two Car objects and prints their brand, model, and year information.


# Ex.No:2(B) METHODS

## QUESTION:
Write a class with one static method and one non-static method. Call both from the main() method.

When staticMethod() is called, it should print  "I am static".

When nonStaticMethod() is called, it should print  "I am non-static"

<img width="169" height="153" alt="image" src="https://github.com/user-attachments/assets/34d50995-5383-43f7-bbe8-2d0716447279" />



## AIM:
To create a Java class with one static method and one non-static method, and demonstrate calling both from the main() method.


## ALGORITHM :
1.	Start the program and define a class MyClass.

2. Create a static method staticMethod() that prints "I am static".

3. Create a non-static method nonStaticMethod() that prints "I am non-static".

4. In the main() method, call the static method directly using the class name.

5. Create an object of MyClass and call the non-static method using this object,        then stop the program.





## PROGRAM:
 ```
/*
Program to implement a Methods using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:

```
public class MyClass {
    public static void staticMethod() {
        System.out.println("I am static");
    }
    public void nonStaticMethod() {
        System.out.println("I am non-static");
    }

    public static void main(String[] args) {
        MyClass.staticMethod();
        MyClass obj = new MyClass();
        obj.nonStaticMethod();
    }
}
```





## OUTPUT:

<img width="415" height="177" alt="image" src="https://github.com/user-attachments/assets/42d4690f-4107-4267-9fa7-b525104e3635" />


## RESULT:
The program successfully calls the static method to print “I am static” and the non-static method to print “I am non-static”.


# Ex.No:2(C) ACCESS SPECIFIERS

## QUESTION:
Write a Java program to create a class called Smartphone with private instance variables brand, model, and storageCapacity. Provide public getter and setter methods to access and modify these variables. Add a method called increaseStorage() that takes an integer value and increases the storageCapacity by that value.

import java.util.Scanner;

class Smartphone {
    private String brand;
    private String model;
    private int storageCapacity;

    
    public String getBrand() {
        return brand;
    }

    public String getModel() {
        return model;
    }

    public int getStorageCapacity() {
        return storageCapacity;
    }

    
    public void setBrand(String brand) {
        this.brand = brand;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public void setStorageCapacity(int storageCapacity) {
        this.storageCapacity = storageCapacity;
    }

   
    public void increaseStorage(int value) {
        if (value > 0) {
            this.storageCapacity += value;
        }
    }

    
    public void display() {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Updated Storage Capacity: " + storageCapacity + " GB");
        System.out.println("------------------------------");
    }
}

//continue your code here


## AIM:
To create a Smartphone class with private attributes and methods to access, modify, and increase storage.


## ALGORITHM :
1. Start the program and create a Smartphone class with private attributes brand,      model, and storageCapacity.

2. Provide getter and setter methods to access and modify the private attributes.

3. Create a method increaseStorage(int value) to add the given value to                storageCapacity.
4. In the main() method, read input from the user for brand, model, storage capacity, and the value to increase storage.

5. Call the increaseStorage() and display() methods to update and show the           smartphone details, then stop the program.





## PROGRAM:
 ```
/*
Program to implement a Access Specifiers using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

class Smartphone {
    private String brand;
    private String model;
    private int storageCapacity;

    public String getBrand() {
        return brand;
    }
    public String getModel() {
        return model;
    }
    public int getStorageCapacity() {
        return storageCapacity;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }
    public void setModel(String model) {
        this.model = model;
    }
    public void setStorageCapacity(int storageCapacity) {
        this.storageCapacity = storageCapacity;
    }

    public void increaseStorage(int value) {
        if (value > 0) {
            this.storageCapacity += value;
        }
    }

    public void display() {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Updated Storage Capacity: " + storageCapacity + " GB");
        System.out.println("------------------------------");
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        Smartphone phone = new Smartphone();
        phone.setBrand(sc.nextLine());
        phone.setModel(sc.nextLine());
        phone.setStorageCapacity(sc.nextInt());

        int increaseValue = sc.nextInt();
        phone.increaseStorage(increaseValue);
        phone.display();
        sc.close();
    }
}
```






## OUTPUT:

<img width="1018" height="456" alt="image" src="https://github.com/user-attachments/assets/624767f6-c2f6-4988-9bbd-ef2b23acfef6" />


## RESULT:
The program updates and displays the smartphone details, including the increased storage.


# Ex.No:2(D) VARIABLE SCOPE AND CONSTRUCTOR

## QUESTION:
Write a program to access a static variable using both class name and object.

<img width="398" height="150" alt="image" src="https://github.com/user-attachments/assets/a94bfbdb-d244-4bc5-9009-f9317c705905" />

## AIM:
To write a Java program that demonstrates accessing a static variable using both the class name and an object of the class.



## ALGORITHM :
1. Start the program and declare a static variable num inside the class prog.

2. In the main() method, read an integer value from the user and assign it to the       static variable num.

3. Access and print the static variable using the class name (prog.num).

4. Create an object of the class (prog obj = new prog();) and access the static         variable using the object (obj.num).

5. Stop the program after displaying the values.





## PROGRAM:
 ```
/*
Program to implement a Variable scope and Constructor using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

class prog {
    
    static int num;

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        num = sc.nextInt();
        System.out.println("Accessing using class name: " + prog.num);

        prog obj = new prog();
        System.out.println("Accessing using object: " + obj.num);

        sc.close();
    }
}

```




## OUTPUT:

<img width="797" height="299" alt="image" src="https://github.com/user-attachments/assets/cc80b0ff-cc27-468a-b2b4-78749a686014" />


## RESULT:
The program successfully shows that a static variable can be accessed directly via the class name and also through an object, producing the same value.


# Ex.No:2(E) ACCESS MODIFIERS

## QUESTION:
Create a class Calculator with: One non-static method add(int a, int b) that returns the sum, One static method info() that says "Calculator is ready".


import java.util.Scanner;

class Calculator {
   // Your Methods here
}

class prog {
    public static void main(String[] args) {
         // Your Function Initiation here
    }
}

<img width="366" height="184" alt="image" src="https://github.com/user-attachments/assets/36a7fca3-e38d-4e39-a418-cebbea122170" />




## AIM:
Create a Calculator class with a non-static add() method to sum two numbers and a static info() method to display a message.


## ALGORITHM :
1.	Start and import Scanner to read input.

2. Define Calculator class with a non-static add(a, b) method and a static info()      method.

3. Read two integers from the user using Scanner.

4. Call Calculator.info() and use a Calculator object to calculate the sum with         add(a, b).

5. Display the sum and end the program.





## PROGRAM:
 ```
/*
Program to implement a Access Modifiers using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:

```
import java.util.Scanner;

class Calculator {
    
    public int add(int a, int b) {
        return a + b;
    }

    public static void info() {
        System.out.println("Calculator is ready");
    }
}

class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int a = sc.nextInt();
        int b = sc.nextInt();

        Calculator.info();

        Calculator calc = new Calculator();
        int sum = calc.add(a, b);

        System.out.println("Sum: " + sum);

        sc.close();
    }
}
```





## OUTPUT:

<img width="576" height="291" alt="image" src="https://github.com/user-attachments/assets/7948428a-1883-4a4c-935e-70ba499028db" />


## RESULT:
The program displays "Calculator is ready", takes two numbers as input, and then shows their sum.
