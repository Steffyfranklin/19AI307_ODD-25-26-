# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:
You wrote a program that stores some input strings into a String array and prints each string in uppercase.
However, you're getting a NullPointerException.
What should you check in your array before calling .toUpperCase() on a element?

## AIM:
To handle a NullPointerException when performing operations on a null string in Java.

## ALGORITHM :
1.	Read a string input from the user.
2.	If the input is "null", assign null to the variable.
3.	Try converting the string to uppercase using toUpperCase().
4.	Catch and handle the NullPointerException if the string is null.
5.	Print "Null element" in case of exception.

## PROGRAM:
 ```
/*
Program to implement a Exception Handling using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

public class NullPointerArrayExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String input = sc.next();
        String str = input.equalsIgnoreCase("null") ? null : input;

        try {
            System.out.println(str.toUpperCase());
        } catch (NullPointerException e) {
            System.out.println("Null element");
        }

        sc.close();
    }
}
```

## OUTPUT:
<img width="1266" height="354" alt="image" src="https://github.com/user-attachments/assets/ca3d287f-7bcc-4852-9515-a3ff25df30a1" />

## RESULT:
The program successfully detects and handles NullPointerException by displaying "Null element" when the input is null.



# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM 

## QUESTION:
At an international airport, only one Radar Control Tower exists. This tower is responsible for handling all flight communications regardless of how many flights are coming in. Each incoming flight must contact this tower to register its approach.

To ensure safety and consistency, all flights must communicate with the same instance of the tower. If multiple towers are created, it may lead to inconsistent instructions — a huge risk in aviation.

Your task is to simulate this system using the Singleton pattern.

Key Hint (Hidden in Story):
Only one control tower object should exist.

Every flight contacting it should register its name.

You should log the order of flights that contacted the tower.

Input Format:
First line: Integer n – number of incoming flights

Next n lines: Each line contains the flight name.

Output Format:
For each flight, print:

[FlightName] registered with Radar Control Tower. Total Flights: [count]

## AIM:
To simulate a radar control system where only one tower instance handles multiple flight communications using the Singleton pattern.

## ALGORITHM :
1.	Create a RadarControlTower class with a private static instance.
2.	Make the constructor private to prevent multiple object creation.
3.	Define a getInstance() method to return the single instance.
4.	Use a registerFlight() method to log flight names and count.
5.	In main(), get the singleton tower instance and register all flights.

## PROGRAM:
 ```
/*
Program to implement a SOLID Principles in Java Program
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.*;

class RadarControlTower {
    private static RadarControlTower instance;
    private int flightCount = 0;

    private RadarControlTower() {}

    public static RadarControlTower getInstance() {
        if (instance == null) {
            instance = new RadarControlTower();
        }
        return instance;
    }

    public int registerFlight(String flightName) {
        flightCount++;
        return flightCount;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();  // consume newline

        for (int i = 0; i < n; i++) {
            String flight = sc.nextLine();
            RadarControlTower tower = RadarControlTower.getInstance();
            int total = tower.registerFlight(flight);
            System.out.println(flight + " registered with Radar Control Tower. Total Flights: " + total);
        }
    }
}

```

## OUTPUT:
<img width="1240" height="326" alt="image" src="https://github.com/user-attachments/assets/9c541c2d-69dd-4cd9-a972-4127d57d2425" />



## RESULT:
The program ensures only one Radar Control Tower instance handles all flight communications and correctly displays the total number of registered flights.



# Ex.No:4(C)  COMPOSITION IN JAVA

## QUESTION:
Create animals from two regions: "Africa" and "Asia". Use Abstract Factory to create families of animals (Herbivore, Carnivore). Print the interaction result.

## AIM:
To demonstrate the Abstract Factory Pattern by creating families of related objects (Herbivore and Carnivore) from two regions — Africa and Asia.

## ALGORITHM :
1.	Define interfaces for Herbivore and Carnivore.
2.	Create concrete classes for African (Zebra, Lion) and Asian (Deer, Tiger) animals.
3.	Define an AnimalFactory interface with methods to create herbivores and carnivores.
4.	Implement concrete factories: AfricaAnimalFactory and AsiaAnimalFactory.
5.	In main(), use factories to create animals and simulate interactions.



## PROGRAM:
 ```
/*
Program to implement a Composition Concepts in Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

interface Herbivore {}
interface Carnivore {
    void eat(Herbivore h);
}

class Wildebeest implements Herbivore {}
class Lion implements Carnivore {
    public void eat(Herbivore h) {
        System.out.println("Lion eats Wildebeest");
    }
}

class Buffalo implements Herbivore {}
class Tiger implements Carnivore {
    public void eat(Herbivore h) {
        System.out.println("Tiger eats Buffalo");
    }
}

interface AnimalFactory {
    Herbivore createHerbivore();
    Carnivore createCarnivore();
}

class AfricaFactory implements AnimalFactory {
    public Herbivore createHerbivore() { return new Wildebeest(); }
    public Carnivore createCarnivore() { return new Lion(); }
}

class AsiaFactory implements AnimalFactory {
    public Herbivore createHerbivore() { return new Buffalo(); }
    public Carnivore createCarnivore() { return new Tiger(); }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String region = sc.nextLine().toLowerCase();
        AnimalFactory factory;

        if (region.equals("africa")) factory = new AfricaFactory();
        else if (region.equals("asia")) factory = new AsiaFactory();
        else {
            System.out.println("Invalid region");
            return;
        }

        Carnivore carn = factory.createCarnivore();
        Herbivore herb = factory.createHerbivore();
        carn.eat(herb);
    }
}

```

## OUTPUT:
<img width="1283" height="337" alt="image" src="https://github.com/user-attachments/assets/85419bff-8dff-4972-b11d-5e2014f6484b" />

## RESULT:
The program successfully demonstrates the Abstract Factory Pattern, showing different animal interactions for Africa and Asia.



# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.

## AIM:
To implement the Factory Design Pattern to send different types of notifications — Email, SMS, and Push.

## ALGORITHM :
1.	Create a Notification interface with the method notifyUser().
2.	Implement this interface in classes EmailNotification, SMSNotification, and PushNotification.
3.	Create a NotificationFactory class to generate objects based on input type.
4.	In main(), read the notification type and get the corresponding object from the factory.
5.	Call the notifyUser() method to send the notification.





## PROGRAM:
 ```
/*
Program to implement a Abstract Factory Pattern using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

interface Notification {
    void notifyUser();
}

class EmailNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Email Notification");
    }
}

class SMSNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending SMS Notification");
    }
}

class PushNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Push Notification");
    }
}

class NotificationFactory {
    public Notification createNotification(String type) {
        switch(type.toLowerCase()) {
            case "email": return new EmailNotification();
            case "sms": return new SMSNotification();
            case "push": return new PushNotification();
            default: return null;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        NotificationFactory factory = new NotificationFactory();
        
        while(true) {
            String input = sc.nextLine();
            if(input.equalsIgnoreCase("exit")) break;

            Notification notification = factory.createNotification(input);
            if(notification != null) {
                notification.notifyUser();
            } else {
                System.out.println("Invalid notification type: " + input);
            }
        }

        sc.close();
    }
}

```






## OUTPUT:
<img width="1284" height="374" alt="image" src="https://github.com/user-attachments/assets/ea1d8e4c-e2a0-40dc-ac41-02cd410c4c07" />



## RESULT:
The program successfully creates and sends the appropriate type of notification using the Factory Pattern.

# Ex.No:4(E) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:
Create an Article class where changes to the content are saved as mementos. Let the user view and restore any saved version.

## AIM:
To implement the Memento Design Pattern that allows saving and restoring versions of an Article object.

## ALGORITHM :
1.	Create ArticleMemento to store article content (state).
2.	Create Article (Originator) that can write, save, and restore content.
3.	Create VersionHistory (Caretaker) to store multiple mementos.
4.	Allow the user to:
5.	Write new content
6.	Save current version
7.	View all saved versions
8.	Restore any version
9.	Display restored version content.

## PROGRAM:
 ```
/*
Program to implement a Behaviour Pattern using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```

import java.util.*;

class Article {
    private String content;

    public Article(String content) {
        this.content = content;
    }

    public void setContent(String content) {
        this.content = content;
    }

    public String getContent() {
        return content;
    }

    public ArticleMemento save() {
        return new ArticleMemento(content);
    }

    public void restore(ArticleMemento memento) {
        this.content = memento.getContent();
    }
}

class ArticleMemento {
    private final String content;

    public ArticleMemento(String content) {
        this.content = content;
    }

    public String getContent() {
        return content;
    }
}

class ArticleHistory {
    private List<ArticleMemento> versions = new ArrayList<>();

    public void saveVersion(Article article) {
        versions.add(article.save());
    }

    public ArticleMemento getVersion(int index) {
        if (index >= 0 && index < versions.size()) {
            return versions.get(index);
        }
        return null;
    }

    public List<ArticleMemento> getAllVersions() {
        return versions;
    }
}

public class ArticleManager {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = Integer.parseInt(sc.nextLine());
        ArticleHistory history = new ArticleHistory();
        Article article = new Article("");

        for (int i = 0; i < n; i++) {
            String content = sc.nextLine();
            article.setContent(content);
            history.saveVersion(article);
        }

        int restoreIndex = Integer.parseInt(sc.nextLine());
        ArticleMemento memento = history.getVersion(restoreIndex);
        if (memento != null) {
            article.restore(memento);
            System.out.println(article.getContent());
        } else {
            System.out.println("Invalid version");
        }

        sc.close();
    }
}

```

## OUTPUT:
<img width="1240" height="593" alt="image" src="https://github.com/user-attachments/assets/1011ef9f-2030-4cf0-af05-89f76ddb4b89" />



## RESULT:
The program successfully demonstrates the Memento Pattern, allowing the user to save, view, and restore different versions of an article.

