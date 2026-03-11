# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:
If an Integer object is set to null, and you attempt to call .toString() on it, what happens? How can you prevent your code from throwing an exception in such cases?


## AIM:

To write a Java program to demonstrate NullPointerException when calling .toString() on a null Integer object and to handle the exception using try-catch.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read an integer value from the user.
4. Assign null if the user enters 0 (or a specific case).
5. Try to call .toString() method on the Integer object.
6. Catch the NullPointerException and display a meaningful message.
7. Display output and end the program.

## PROGRAM:
 ```
Program to implement a Exception Handling using Java
Developed by: Syed Abu Hanifa
Register Number: 212224040346 
```

## SOURCE CODE:
``` java
import java.util.Scanner;

public class NullCheck
{
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        Integer num = sc.nextInt(); 
        try 
        {
            if (num == 0) 
            {
                num = null;
            }
            System.out.println(num.toString());

        } 
        catch (NullPointerException e) 
        {
            System.out.println("Null Integer");
        }
    }
}
```






## OUTPUT:
![java41](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/9322907efbe6666ef88acb6049076b422ed172f1/19AI307_JAVA(25-26)/Module-04/DAY-1/java41.png)


## RESULT:
Thus, the program demonstrates that calling .toString() on a null object causes a NullPointerException, and the exception can be prevented using a try-catch block.


# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM 

## QUESTION:
In a large office, multiple departments send print jobs to a shared central printer. To manage load and prevent collision, a Print Spooler Manager handles all job submissions.

The IT team insists that there should be only one spooler manager instance in the entire system. Regardless of how many jobs or departments exist, all jobs must pass through this one manager.

Your task is to simulate a singleton print job queue. Each print job submitted increases the queue count.

## AIM:
To write a Java program that demonstrates the Singleton Design Pattern, ensuring only one instance of a Print Spooler Manager exists to handle job queue management.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a PrintSpooler class with:

    A private static instance.

    A private constructor.

    A public static getInstance() method to return the single instance.

4. Maintain a counter that represents the number of print jobs.
5. In the main() method, simulate two departments submitting print jobs.
6. Access the same instance of the Print Spooler and increment the job count.
7. Display the print job queue.
8. Stop the program.



## PROGRAM:
 ```
Program to implement a SOLID Principles in Java Program
Developed by: Syed Abu Hanifa
Register Number: 212224040346
```

## SOURCE CODE:
``` java
import java.util.*;

class PrintSpoolerManager {
    private static PrintSpoolerManager instance;
    private int jobCount = 0;

    private PrintSpoolerManager() {}

    public static PrintSpoolerManager getInstance() {
        if (instance == null) {
            instance = new PrintSpoolerManager();
        }
        return instance;
    }

    public int submitJob(String department) {
        jobCount++;
        return jobCount;
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            String dept = sc.nextLine();
            PrintSpoolerManager spooler = PrintSpoolerManager.getInstance();
            int total = spooler.submitJob(dept);
            System.out.println(dept + " submitted a print job. Total Jobs in Queue: " + total);
        }
    }
}
```


## OUTPUT:

![java42](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/307e4889adff0712306078adcc9b86614a3f814f/19AI307_JAVA(25-26)/Module-04/DAY-2/java42.png)

## RESULT:
Thus, the program to simulate a Singleton Print Spooler Manager using SOLID principles was successfully implemented and executed.


# Ex.No:4(C)  COMPOSITION IN JAVA

## QUESTION:
Create animals from two regions: "Africa" and "Asia". Use Abstract Factory to create families of animals (Herbivore, Carnivore). Print the interaction result.



## AIM:
To write a Java program demonstrating Composition and Abstract Factory Pattern by creating animal families of different regions and displaying interactions between herbivores and carnivores.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create interfaces Herbivore and Carnivore.
4. Create concrete animal classes (e.g., Wildebeest, Lion, Deer, Tiger) implementing those interfaces.
5. Create an abstract factory class for producing families of animals.
6. Implement region-based factories (AfricaFactory, AsiaFactory).
7. In the main program, instantiate factories and show interactions.
8. Print the result.
9. Stop the program.

## PROGRAM:
 ```
Program to implement a Composition Concepts in Java
Developed by: Syed Abu Hanifa
Register Number: 212224040346
```

## SOURCE CODE:
``` java
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

![java43](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/8b4be1e27b6fb5da0aa68915801ab1e6c9c7174e/19AI307_JAVA(25-26)/Module-04/DAY-3/java43.png)

## RESULT:
Thus, the program using Composition and Abstract Factory Pattern was successfully implemented and executed to create animal interactions for African and Asian regions.


# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
Create a system that builds Car and Bike objects for two companies: "Honda" and "Yamaha". Use Abstract Factory Pattern to choose the brand and output the type and brand for each vehicle.


## AIM:
To write a Java program demonstrating Abstract Factory Pattern by creating related objects (Car and Bike) without specifying their concrete classes.


## ALGORITHM :
1. Create Car and Bike interfaces
2. Implement these interfaces for Honda and Yamaha
3. Create Abstract Factory (VehicleFactory)
4. Implement concrete factories (HondaFactory, YamahaFactory)
5. Use FactoryProducer to get the required factory
6. Create Car and Bike objects using the factory
7. Display the output

## PROGRAM:
 ```
Program to implement a Composition Concepts in Java
Developed by: Syed Abu Hanifa
Register Number: 212224040346
```

## SOURCE CODE:
``` java
import java.util.*;
interface Car{
    void create();
}
interface Bike{
    void create();
}

class HondaCar implements Car{
    public void create()
    {
        System.out.println("Honda Car created");
    }
}
class HondaBike implements Bike{
    public void create()
    {
        System.out.println("Honda Bike created");
    }
}

class YamahaCar implements Car{
    public void create()
    {
        System.out.println("Yamaha Car created");
    }
}
class YamahaBike implements Bike{
    public void create()
    {
        System.out.println("Yamaha Bike created");
    }
}

interface VehicleFactory{
    Car createCar();
    Bike createBike();
}

class HondaFactory implements VehicleFactory{
    public Car createCar()
    {
        return new HondaCar();
    }
    public Bike createBike()
    {
        return new HondaBike();
    }
}

class YamahaFactory implements VehicleFactory{
    public Car createCar()
    {
        return new YamahaCar();
    }
    public Bike createBike()
    {
        return new YamahaBike();
    }
}

class FactoryProducer{
    public static VehicleFactory getFactory(String brand)
    {
        if(brand==null) return null;
        switch(brand.toLowerCase())
        {
            case "honda":
                return new HondaFactory();
            case "yamaha":
                return new YamahaFactory();
            default:
                return null;
        }
    }
}

public class Main{
    public static void main(String args[])
    {
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextLine())
        {
        String input = sc.nextLine();
        if(input.isEmpty()) continue;
        VehicleFactory fac = FactoryProducer.getFactory(input);
        
        if (fac!=null)
        {
            fac.createCar().create();
            fac.createBike().create();
        }
        else
        {
            System.out.println("Invalid company");
        }
        }
    }
}
```





## OUTPUT:

![java43](https://github.com/Yamunaasri/19AI307_ODD-25-26-/blob/main/19AI307_JAVA(25-26)/Module-04/Screenshot%202025-11-22%20110051.png)



## RESULT:
Thus, the program using Abstract Factory Pattern was successfully implemented and executed to create related objects (Car and Bike) without specifying their concrete classes.


# Ex.No:4(D) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:
Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.



## AIM:
To write a Java program that demonstrates a Behavioral Pattern using the Factory Method, allowing different notification types to send messages through a common interface.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an interface Notification with method notifyUser().
4. Implement concrete classes: EmailNotification, SMSNotification, and PushNotification.
5. Create a NotificationFactory that returns the appropriate object based on user input.
6. In main(), get the notification type from the user.
7. Call the notifyUser() method of the returned object.
8. If no valid type is provided, display an error.
9. Stop the program.





## PROGRAM:
 ```
Program to implement a Behaviour Pattern using Java
Developed by: Syed Abu Hanifa
Register Number: 212224040346
```

## SOURCE CODE:
``` java
import java.util.Scanner;

interface Notification {
    void notifyUser();
}

// ===== Concrete Notifications =====
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

// ===== Factory =====
class NotificationFactory {
    public Notification createNotification(String type) {
        if (type == null) return null;
        switch (type.toLowerCase()) {
            case "email":
                return new EmailNotification();
            case "sms":
                return new SMSNotification();
            case "push":
                return new PushNotification();
            default:
                return null;
        }
    }
}

// ===== Main =====
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        NotificationFactory factory = new NotificationFactory();

        while (true) {
            String input = sc.nextLine().trim();
            if (input.equalsIgnoreCase("exit")) break;

            Notification n = factory.createNotification(input);
            if (n != null) {
                n.notifyUser();
            } else {
                System.out.println("Invalid notification type: " + input);
            }
        }

        sc.close();
    }
}
```






## OUTPUT:

![java45](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/c6316a5904f4a174dd995f6b7d7c47b65f677921/19AI307_JAVA(25-26)/Module-04/DAY-5/java45.png)

## RESULT:
Thus, the program demonstrating the Behavioral Pattern using Factory Method to generate different notification types was successfully implemented and executed.
