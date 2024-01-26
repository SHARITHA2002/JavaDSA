## Basic Maths

 1) Count Digits => Length of the digits:(int)Math.log10(n)+1
 2) Reverse a number
 3) Check palindrome
 4) Armstrong number
 5) Print all divisors
 6) Check for prime
 7) GCD or HCF 

## Finding Digits

  ```
    int n=7789;
    while(n>0)
    {
      int rem=n%10;
      system.out.print(rem);
      n=n/10;
    }
    
  ```

Output:

```
7 7 8  9
```
- While finding digits, the magic number is 10 because of units 0s 10s 100s 1000s in a number

## Finding Binary

```
  temp=n%2;
  n/=2;
```

- Here 2 represents Binary,8 for Octal,16 for hexadecimal



## Counting a digit

     int temp=n;
        int count=0;
        while(temp>0)
        {
            int rem=temp%10;
            if(rem!=0)
            {
                if(n%rem==0)
                {
                     count++;
                }
            }
            temp/=10;
        }
        return count;
      // n=35; ans=1 since 35  is only divisible  by 5
      // n=336 ; ans=3 since 336 divisible by both 3,3 & 6;

## Reverse a Number

```
int n=123;
int rev=0;
while(n>0)
{
  int rem=n%10;
  rev=(rev*10)+rem;
  n/=10;
}
// n=321
```
- in case of a -ve number make sure that the number is in the range check, n< Integer.MAX_LENGTH/10 || n>Integer.MIN_LENGTH/10

  ## 	Check Palindrome

  - For palindrome checking make sure that the given number is backed up as a dup number, Finally check the dup number with reverse no
  - Because while making changes in the given number eventually it becomes 0.
 
## 	Armstrong Numbers

  - For Armstrong number,use ans+= reminder * reminder *reminder instead of Math.pow(rem,3);
  - return ans==number?true:false

## Divisors



## GCD or HCF 

  - Two approaches :
  1) FInd min of 2 number, until min number, check if element divides both n &m
  2) Eucledian algorithm : gcd(a,b)=gcd(a-b,b) ,if(a>b)

     ```
         while(n>0 && m>0)
         {
           if(n>m) n%=m;
           else    m%=n
         }

         if(n==0) return m;
         else return n;
     ```

  - Time complexity: O(log <sub>pi</sub> min(a,b))
