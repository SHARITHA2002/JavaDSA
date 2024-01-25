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

