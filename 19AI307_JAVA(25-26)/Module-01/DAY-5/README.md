# Ex.No:1(E) STRINGS AND MATH FUNCTION

## QUESTION:

Write a Java program to calculate the power of a given number.


## AIM:
To write a Java program to compute the power of a number using the Math.pow() function in Java.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the base value from the user.
4. Read the exponent value from the user.
5. Use the Math.pow(base, exponent) function to calculate the power.
6. Display the result.
7. Stop the program.

## PROGRAM:
 ```
Program to implement a Strings and Math Function using Java
Name: Syed Abu Hanifa
Register Number: 212224040346
```

## SOURCE CODE:

``` java
import java.util.*;

public class PowerCalculation {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        double base = sc.nextDouble();
        double exponent = sc.nextDouble();
        double result = Math.pow(base, exponent);

        System.out.println(base + " raised to the power of " + exponent + " is: " + result);
    }
}

```





## OUTPUT:
![Screenshot 2025-11-17 002442](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/48e3a0e8c1eaa81a22e732def7d6ac38d8c6d9ba/19AI307_JAVA(25-26)/Module-01/DAY-5/Screenshot%202025-11-17%20002442.png)


## RESULT:
Thus, the Java program to calculate the power of a given number using Math function was successfully executed.









