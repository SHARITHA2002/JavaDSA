## Recursions

  - It is a phenomenon when a function calls itself indefinitely until a specified condition is fulfilled.
  - What is Stack Overflow in Recursion?
        - It is a condition that occurs when a function calls itself, there are no base conditions to stop the call;
  - **Recursive Tree**
        - It is a diagrammatic representation of the recursion calls
    
      <img src="https://takeuforward.org/wp-content/uploads/2023/02/image-5.png" alt="RecursionTree" height=250 width=250>

  - Recursion - Practice Problems 🏋️
    
             
                1.Print 1 to N using recursion 
                2.Print N to 1 using recursion 
                3.Sum of first N numbers 
                4.Factorial of N numbers 
                5.Reverse an array 
                6.Check if a string is palindrome or not 
                7.Fibonacci number 
             

     ## Print 1 to N using Recursion

      - Idea 💡:
        - Normally we can use the loops to iterate the numbers, but the condition without using loops.
        - But three things remain the same [intialization, condition, increment]
        - Here comes recursion in play, just pass the initialized count & number to the function
        - Inside the function call the function itself until the count becomes less than n & when the condition does not match, return the array.
        - And increment the count value while calling itself.
        
      - Code 👩‍💻:

            public class Solution
            {
                public static int[] printNos(int x)
                {
                   int count=1;
                   int[] nums=new int[x];
                   
                   return add(nums,count,x);
                }
            
                public static int[] add(int[] nums,int count,int x)
                {
                    if(count>x) //Condition
                    {
                        return nums;
                    }
                    nums[count-1]=count; //Operation
                    return add(nums,count+1,x); // Increment
                }
            }

    


    ## Print N to 1 using recursion

      - Idea 💡:
        
        - Normally we can use the loops to iterate the numbers, but the condition without using loops.
        - But three things remain the same [intialization, condition, increment]
        - Here comes recursion in play, just pass the count [i.e if n=5, count also 5] & number to the function
        - Inside the function call the function itself until the count becomes greater than 1 & when the condition not matches return the array.
        - And decrement the count value while calling itself.
          
      - Code 👩‍💻:

              public static int[] printNos(int x)
                {
                  int[] nums=new int[x];
                  int count=x;
                  return add(nums,count,x);
                }

              public static int[] add(int[] nums,int count,int x)
              {
                  if(count<1)
                  {
                      return nums;
                  }
                  nums[x-count]=count;
                  return add(nums,count-1,x);
              }

    ## Sum of first N numbers 

      - Idea 💡:
         - Try to solve it using the math formula.
         - Sum of first n natural numbers= n*(n-1),if n==0,return 0
          
      - Code 👩‍💻:

                 public static long sumFirstN(long n)
                 {
                    return sum(n);
                 }

                public static long sum(long n)
                {
                    if(n==0)
                    {
                        return 0;
                    }
                    return n+sum(n-1);
                }


    ## Factorial of first n number

    - Idea 💡:
         - Try to solve it using the math formula.
         - n*(n-1),if n==0 return 1;
          
    - Code 👩‍💻:

            public static List<Long> factorialNumbers(long n) 
              {
                  ArrayList<Long> arr=new ArrayList<>();
                  for(long i=1;i<=n;i++)
                  {
                      if(fact(i)>n)
                      {
                         return arr;
                      }
                       arr.add(fact(i));
                  }
                  return arr;
              }
          
              public static long fact(long i)
              {
                  if(i==0)
                  {
                      return 1;
                  }
                  return i*fact(i-1);
              }


    ## Reverse an array

      - Idea 💡:
         - Create a recursive function that gets an array, start& end of an array
         - Start obviously 0 and end arr.length-1.Pass these params to the recursive function
         - Function calls itself until [start<end] which means when the start & end pointers travel in the opposite direction,@ that point we can confirm that I traversed half of the array.
         - Inside the function, try to swap both the two pointer values[start & end].
         - While calling the function itself, increment the start ptr by +1 & end ptr by -1 => for iterating throughout the loop.
          
      - Code 👩‍💻:

            public static int[] reverseArray(int n, int []nums)
            {
                int start=0;
                int end=nums.length-1;
                return reverse(nums,start,end);
            }

            public static int[] reverse(int[] nums, int start,int end)
            {
                if(start>end)
                {
                    return nums;
                }
                int temp=nums[start];
                nums[start]=nums[end];
                nums[end]=temp;
        
                return reverse(nums,start+1,end-1);
            }

    ## String-Palindrome or not

     - Idea 💡:
         - Same as swapping an array, but the only thing is there is no need for swapping, only checking
         - if the 2 char are not same return false, if the ptr crosses half of the string without falling in the condition, returns true
          
      - Code 👩‍💻:

            public static boolean isPalindrome(String str)
            {
                int i=0;
                return isPal(str,i);
            }
    
            public static boolean isPal(String str,int i)
              {
                  if(i>str.length()/2)
                  {
                          return true;
                  }
      
              if(str.charAt(i)!=str.charAt(str.length()-i-1))
              {
                      return false;
              }
      
              return isPal(str,i+1);
          }

    ## Fibonacci number
      
     - Idea 💡:
         - Use the Math formula : f(n-1)+f(n-2)
         - In fibonacci, always f[0]=0; f[1]=1; f[2]=1;
         - Example: if n=5 : 0,1,1,2,3
          
      - Code 👩‍💻:
   
              public int fib(int n)
              {
                  return fibbo(n);
              }
    
              public static int fibbo(int n)
              {
                  if(n<=1)
                  {
                      return n;
                  }
                  return fibbo(n-1)+fibbo(n-2);
              }
