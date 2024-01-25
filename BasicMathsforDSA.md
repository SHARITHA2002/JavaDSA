## Euclidian Algorithm

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

  - For Armstrong number,use reminder * reminder *reminder instead of Math.pow(rem,3);
