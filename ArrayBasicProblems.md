## Arrays Basic Problems 🧮

## Find the Largest element in an array 🌲

**Brute Force Approach:💡**
- Sort the array in an ascending order using any of the sorting algo & return the last index (arr[n-1])
- Time complexity  : O(n log n) Space Complexity : O(1)

**Optimal Approach:💡**
- set a variable with an Integer.MIN_VALUE & start iterating the loop & compare it with every value of the arr, if any of the values is > than Max, replace max with the current value of arr.
- Time complexity  : O(log n) Space Complexity : O(1)

**Code👩🏻‍💻**

     int max=Integer.MIN_VALUE;
        for(int i=0;i<n;i++)
        {
            if(arr[i]>max)
            {
                max=arr[i];
            }
        }
        return max;

**Link🔗:** <a href="https://www.codingninjas.com/studio/problems/largest-element-in-the-array-largest-element-in-the-array_5026279?utm_source=striver">Find the Largest element in an array</a>

## Find the Second Largest element in an array 🌲🌲

**Brute Force Approach:💡**
- Sort the array in an ascending order using any of the sorting algo
- Start Iterating the loop in reverse, if the element is greater than secondLargest element & not equal to the largest element return the secondLargest & break the loop;
- Time complexity  : O(n log n) Space Complexity : O(1)

**Better Approach:💡**
- First find the largest element in an array, for the 2nd pass start traversing the loop, if the element is greater than 2nd Largest && not equal to the largest element, return the element.
- Time complexity  : O(2n) Space Complexity : O(1)

**Code 👩🏻‍💻**

     public static int findSecondMax(int[] a,int n)
    {       
        int max=Integer.MIN_VALUE;
        int secMax=Integer.MIN_VALUE;

       for(int i=0;i<n;i++)
       {
           if(a[i]>max)
           {
               max=a[i];
           }
       }
        for(int j=0;j<n;j++)
           {
              if(a[j]>secMax && a[j]!=max)
                {
                    secMax=a[j];
                }
           }
        return secMax;
    }

**Optimal Approach:💡**
- Initialize the largest & secondLargest with Integer.MIN_VALUE & start Iterate the given array.
- If the element is greater than the largest element replace secondLargest element with the largest element (previous largest) && the largest element with that element
- If the element is greater than secondLargest element && that element is not the same as the largest element, then replace secondLargest elemnt with that element.
- Time complexity  : O(n) Space Complexity : O(1)

**Code👩🏻‍💻**

     public static int findSecondMax(int[] a,int n)
    {       
        int max=Integer.MIN_VALUE;
        int secMax=Integer.MIN_VALUE;

       for(int i=0;i<n;i++)
       {
           if(a[i]>max)
           {
               secMax=max; //Previous Max
               max=a[i];
           }
           if(a[i]>secMax && a[i]!=max)
           {
                secMax=a[i];
           }
       }
        return secMax;
    }

**Link🔗:** <a href="https://www.codingninjas.com/studio/problems/ninja-and-the-second-order-elements_6581960?utm_source=striver">Find the Second Largest element in an array</a>



## Check if the Array Is Sorted and Rotated 📊

**Idea💡**
- For rotations, 🔑 things are if the array is sorted, the 1st element > the last element.
- The next condition would be that only one element in an array, should be greater than the previous element i.e.) [7,2,4,6] Here @ only once,7 is greater than 2 otherwise both sides are in ascending order.
  
**Code👩🏻‍💻**

     int count = 0;
     boolean result = false;

        // Sorted or not
        if (nums[nums.length - 1] > nums[0]) {
            count++;
        }
        for (int i = 1; i < nums.length; i++) {
            if (nums[i - 1] > nums[i]) {
                count++;
            }
        }

        // Rotation check
        if (count <= 1) {
            result = true;
        }
        return result;
    }
    

**Link🔗:** <a href="https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/description/">Find if the array is sorted & rotated </a>
     
