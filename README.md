# Find-all-the-Prime-Numbers-in-a-Given-Interval-in-Java

Given two integer inputs for the range or the interval for the search. The objective is to search and find all the Prime Numbers that lay in the given interval or range. To do so we’ll iterate through the numbers and check whether or not they are prime simultaneously. We’ll use loops to check whether the number has any factors other than 1 and the number itself. Here are few methods we’ll use to Find all the Prime Number in a Given Interval in Java Language.

Method 1: Using inner loop Range as [2, number-1].
Method 2: Using inner loop Range as [2, number/2].
Method 3: Using inner loop Range as [2, sqrt(number)].
Method 4: Using inner loop Range as [3, sqrt(number), 2].
We’ll discuss the above mentioned methods in the sections mentioned below.

Method 1: Using inner loop Range as [2, number-1]
Working
For two integer variables lower and higher we perform the following,

We run a loop  to iterate through the number in the given interval.
We check if the number is a prime by checking for factors within the range.
Let’s implement the above mentioned logic in Java Language.

Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     int lower = 1, upper = 20;


     for (int i = lower; i <= upper; i++)
       if (isPrime (i))
        System.out.println (i);
   }

   static boolean isPrime (int n)
   {
     int count = 0;

     // 0, 1 negative numbers are not prime
     if (n < 2)
       return false;

     // checking the number of divisors b/w 1 and the number n-1
     for (int i = 2; i < n; i++)
       {
     if (n % i == 0)
        return false;
       }

     // if reached here then must be true
     return true;
   }
 }
Output
2 3 5 7 11 13 17 19
Related Pages
Leap year

Prime Number

Sum of Digits of a number

Reverse of a number

Palindrome number

Method 2: Using inner loop Range as [2, number/2]
Working
For a given two integers lower and upper we perform the following,

We iterate through the numbers using for loop.
We check whether or not the number has a factor within the range [2, number/2].
Let’s implement the above mentioned logic in Java Language.

Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     int lower = 1, upper = 20;


     for (int i = lower; i <= upper; i++)
       if (isPrime (i))
        System.out.println (i);
   }

   static boolean isPrime (int n)
   {
     int count = 0;

     // 0, 1 negative numbers are not prime
    if (n < 2)
       return false;

     // checking the number of divisors b/w 1 and the number n
     for (int i = 2; i < n / 2; i++)
       {
      if (n % i == 0)
        return false;
       }

     // if reached here then must be true
     return true;
   }
 }
Output
2 3 5 7 11 13 17 19
Method 3: Using inner loop Range as [2, sqrt(number)]
Working
For the two given integer variables lower and upper we perform the following,

We iterate through the numbers using a for loop.
We check whether or not the number has factors in the interval [2, sqrt(number)].
Let’s implement the above mentioned logic in Java Language.

Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     int lower = 1, upper = 20;


     for (int i = lower; i <= upper; i++)
       if (isPrime (i))
 	  System.out.println (i);
   }

   static boolean isPrime (int n)
   {
     int count = 0;

     // 0, 1 negative numbers are not prime
     if (n < 2)
       return false;

     // A number n is not a prime, if it can be factored into two factors a & b:
     // n = a * b

     /*Now a and b can't be both greater than the square root of n, since
       then the product a * b would be greater than sqrt(n) * sqrt(n) = n.
       So in any factorization of n, at least one of the factors must be
       smaller than the square root of n, and if we can't find any factors
       less than or equal to the square root, n must be a prime.
      */
     for (int i = 2; i < Math.sqrt (n); i++)
       {
 	if (n % i == 0)
 	  return false;
       }

     // if reached here then must be true
     return true;
   }
 }
Output
2 3 5 7 11 13 17 19
Method 4: Using inner loop Range as [3, sqrt(number), 2]
Working
For the two given integer variables lower and upper, we perform the following,

Iterate through the numbers using for loop with the step size as 2.
Check if the number has any factors in the range [3, sqrt(number)].
Let’s implement the above logic in Java Language.

Java Code
Run
public class Main
{
  public static void main (String[]args)
  {

    int lower = 1, upper = 20;


    for (int i = lower; i <= upper; i++)
      if (isPrime (i))
	  System.out.println (i);
  }

  static boolean isPrime (int n)
  {
    // 0 and 1 are not prime numbers
    // negative numbers are not prime
    if (n <= 1)
        return false;

    // special case as 2 is the only even number that is prime
    else if (n == 2)
        return true;

    // Check if n is a multiple of 2 thus all these won't be prime
    else if (n % 2 == 0)
        return false;

    // If not, then just check the odds
    for (int i = 3; i <= Math.sqrt(n); i += 2)
    {
        if (n % i == 0)
            return false;
    }
    
    return true;
}
}
Output
 2 3 4 5 7 11 13 17 19



