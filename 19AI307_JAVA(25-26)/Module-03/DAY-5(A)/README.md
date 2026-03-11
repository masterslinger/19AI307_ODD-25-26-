# Ex.No:3(E) INNER CLASS

## QUESTION:
Write a Java program to reverse a number using the Integer wrapper class and compare it with the original number.


## AIM:
To write a Java program to check whether a given number is a Palindrome or not using Inner Class.

## ALGORITHM
1. Start
2. Read an integer value from the user
3. Convert the number into a String
4. Reverse the String
5. Convert the reversed String back to integer
6. Compare the original number with reversed number
7. If both are equal, it is a Palindrome
8. Else, it is not a Palindrome
9. Stop

## PROGRAM:
 ```
Program to implement a InnerClass using Java
Developed by: Syed Abu Hanifa
RegisterNumber: 212224040346
```

## SOURCE CODE
``` java
import java.util.*;
class prog{
    public static void main(String args[])
    {
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();
        String originalStr = Integer.toString(num);
        String reversedStr = new StringBuilder(originalStr).reverse().toString();
        int reversedNum = Integer.parseInt(reversedStr);
        if(num == reversedNum)
        {
            System.out.println(num+" is a palindrome number.");
        }
        else{
            System.out.println(num+" is not a palindrome number.");
            System.out.println("Reversed Number: "+reversedNum);
        }
    }
}
```

## OUTPUT:

![Program Output](https://github.com/Yamunaasri/19AI307_ODD-25-26-/blob/main/19AI307_JAVA(25-26)/Module-03/Screenshot%202025-11-22%20103338.png)

## RESULT
Thus, the Java program to check whether a number is a Palindrome was successfully executed.


