## Recursions

  - It is a phenomenon when a function calls itself indefinitely until a specified condition is fulfilled.
  - What is Stack Overflow in Recursion?
        - It is a condition that occurs when a function calls itself, there are no base conditions to stop the call;
  - **Recursive Tree**
        - It is a diagrammatic representation of the recursion calls
    
      <img src="https://takeuforward.org/wp-content/uploads/2023/02/image-5.png" alt="RecursionTree" height=250 width=250>

  - Recurion - Practice Problems
     <ol type="1">
        <li>Print 1 to N using recursion</li>
       <li>Print N to 1 using recursion</li>
       <li>Sum of first N numbers</li>
       <li>Factorial of N numbers</li>
       <li>Reverse an array</li>
       <li>Check if a string is palindrome or not</li>
       <li>Fibonacci number</li>
     </ol>

     ## Print 1 to N using Recursion

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

       - Try to using the formula .Sum of first n natural numbers= n*(n-1),if n==0,return 0

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

    Example : n=7 output:[1,2,6]
    - Remember the formula -> n*(n-1) but if n==0 return 1;

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


          
