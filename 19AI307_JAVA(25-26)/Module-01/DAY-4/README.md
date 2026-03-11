# Ex.No:1(D) ARRAYS

## QUESTION:
Write a Java program to find the index of a given element in an array.

## AIM:
To write a Java program that finds the index position of a specified element from a given array.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the size of the array from the user.
4. Create an array of the given size.
5. Read the array elements from the user and store them in the array.
6. Read the element to be searched.
7. Traverse the array and compare each element with the search element.
8. If matched, print the index position and terminate.
9. If not found, display "Element not found".
10. Stop the program.

## PROGRAM:
 ``` 
Program to implement a Array concept using Java
Name: Syed Abu Hanifa
Register Number: 212224040346
```

## SOURCE CODE:
``` java
import java.util.*;
public class Main
{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int[] arr=new int[n];
        for(int i=0;i<n;i++)
        {
            arr[i]=sc.nextInt();
        }
        int key=sc.nextInt();
        int index=-1;
        for(int i=0;i<n;i++)
        {
            if(arr[i]==key)
            {
                index=i;
                break;
            }
        }
        
        if(index!=-1)
        {
            
            System.out.println(index);
        }
        else{
            System.out.println("Element not found");
        }
    }
}
```







## OUTPUT:
![OUTPUT](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/89cca4a56df2cfb4774052b6ca0e2fe103f4875f/19AI307_JAVA(25-26)/Module-01/DAY-4/output.jpg)

## RESULT:

Thus, the Java program to find the index of a given element in an array was successfully executed.






