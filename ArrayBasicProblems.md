## Arrays Basic Problems 🧮

## 1)Find the Largest element in an array 🌲

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

## 2)Find the Second Largest element in an array 🌲🌲

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



## 3)Check if the Array Is Sorted and Rotated 📊

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


## 4)Remove Duplicates from Sorted Array

**Idea💡**
- we have to remove the duplicates **in-place** such that each unique element appears only once. The relative order of the elements should be kept the same.
- We can go with the 2 pointer approach. For that, we initialize 1st ptr as 1 & start traversing the array, if current & previous elements are not equal, increment 1st ptr & replace the element in 1st ptr's position.
  
**Code👩🏻‍💻**

     int ptr1=1;
     for (int ptr2 = 1; ptr2< nums.length; ptr2++) {
            if (nums[ptr2 - 1] !=nums[ptr2]) {
                ptr1++;
                nums[ptr1]=nums[ptr2];
            }
        }
        return ptr1;
    }

**Link🔗:** <a href="https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/description/"> Remove Duplicates from Sorted Array</a>



## 4)Rotate Array

**Idea💡**
- Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.
- Input: nums = [1,2,3,4,5,6,7], k = 3 ,Output: [5,6,7,1,2,3,4]
- Explanation:
  
     rotate 1 step to the right: [7,1,2,3,4,5,6]
     
     rotate 2 steps to the right: [6,7,1,2,3,4,5]
     
     rotate 3 steps to the right: [5,6,7,1,2,3,4]
  
-  First, reduce key to key%arr. length then reverse the whole array
-  Secondly, reverse the array from 0 to key-1
-  Finally, reverse the array from key to arr. length -1;
  
**Code👩🏻‍💻**

        k%=nums.length;
        rotateArray(nums,0,nums.length-1);
        rotateArray(nums,0,k-1);
        rotateArray(nums,k,nums.length-1);

        public void rotateArray(int[] nums,int start,int end)
         {
             while(start<end)
             {
                 int temp=nums[start];
                 nums[start]=nums[end];
                 nums[end]=temp;
                 start++;
                 end--;
             }
         }
   

**Link🔗:** <a href="https://leetcode.com/problems/rotate-array/description/"> Rotate Array</a>
