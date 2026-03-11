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




