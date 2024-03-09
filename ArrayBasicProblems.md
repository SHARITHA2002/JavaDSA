## Arrays Basic Problems 🧮
   
        1) Find the Largest element in an array🎄
        2) Find the Second Largest element in an array 🌲🌲
        3) Check if the Array Is Sorted and Rotated 📊
        4) Remove Duplicates from Sorted Array👨🏽‍🤝‍👨🏼
        5) Rotate Array⭕
        6) Move Zeroes  🤜🏻0
        7) Union of Arrays 💠
        8) Intersection of Two Arrays 🧩
        9) Missing Number 🔍

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
- If the element is greater than secondLargest element && that element is not the same as the largest element, then replace the second largest elemnt with that element.
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


## 4)Remove Duplicates from Sorted Array👨🏽‍🤝‍👨🏼

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



## 5)Rotate Array⭕

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

        k %= nums.length;  // Ensure k is within the range of array length
        rotateArray(nums, 0, nums.length - 1);  // Rotate the entire array
        rotateArray(nums, 0, k - 1);  // Rotate the first k elements
        rotateArray(nums, k, nums.length - 1);  // Rotate the remaining elements

        public void rotateArray(int[] nums, int start, int end)
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


## 6)Move Zeroes 

- Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.
- Input: nums = [0,1,0,3,12] Output: [1,3,12,0,0]

**Idea💡**

-  There are 2 approaches are there,
     
-  **Brute force approach:**

   - Creating new arr with a size of the given array & ptr with value 0
   - Start iterating the given arr, if any non-zero element is found, add it to the temp array in the ptr index & increment the ptr.
   - At last, the other positions in the array are automatically filled with the value 0 [BY default in Java while array declaration all the values are filled with 0]
   - Code👩🏻‍💻:
           
                 int[] temp=new int[a.length];
                 int j=0;
                 for(int i=0;i<a.length;i++)
                 {
                     if(a[i]!=0)
                     {
                         temp[j]=a[i];
                         j++;
                     }
                 }
                 return temp;
           
-  **Optimal approach:**

   -  In this approach, normal swapping is the key., The only condition is when the ptr meets the non-zero element, then only swapping has to be done
   -  So initialize a ptr with a value of 0 & start iterating the array, when it meets the non-zero elemnt just swap arr[ptr] with a non-zero value & increment the ptr;
   -  Code 👩🏻‍💻:

                  int j=0;
                  for(int i=0;i<nums.length;i++)
                  {
                      if(nums[i]!=0)
                      {
                          int temp=nums[j];
                          nums[j]=nums[i];
                          nums[i]=temp;
                          j++;
                      }
                  }

**Link🔗:** <a href="https://leetcode.com/problems/move-zeroes/">Move Zeroes</a>

## 7)Merge 2 Sorted Array 💠

- Given two sorted arrays, ‘a’ and ‘b’, of size ‘n’ and ‘m’, respectively, return the union of the arrays.
- Input: a= [1, 2, 3, 4, 6], b = [2, 3, 5] Output: [1, 2, 3, 4, 5, 6]

**Idea💡**
   -  In simple, we have to initialize 2 ptr for the 2 arrays & one array list for adding the unique elements.
   -  We have to Do the operations until our ptrs are less than the length of that array.
   -  Inside, then start checking if the  element is the 1st element in the array list or the previous element of the array list & the current element of the array are not the same,if then add the elemnt to the array list & also increment the pointers
   -  If any one of  the arrays becomes greater than the length of the array, then no more comparison is required with the other array, just push the elements by only checking if they already exist, otherwise add it to the array list. 
   -  Code 👩🏻‍💻:

                  ArrayList<Integer> arr=new ArrayList<>();
                  int i=0;
                  int j=0;
                  int n1=a.length;
                  int n2=b.length;
                  while(i<n1 && j<n2)
                  {
                      if(a[i]<=b[j])
                      {
                         if(arr.size()==0 || arr.get(arr.size()-1)!=a[i])
                          {
                              arr.add(a[i]);
                          }
                          i++;
                      }
                      else
                      {
                           if(arr.size()==0 || arr.get(arr.size()-1)!=b[j])
                          {
                              arr.add(b[j]);
                          }
                          j++;
                      }
                  }
                  while(i<n1)
                  {
                      if(arr.size()==0 || arr.get(arr.size()-1)!=a[i])
                          {
                              arr.add(a[i]);
                          }
                          i++;
                  }
                  while(j<n2)
                  {
                       if(arr.size()==0 || arr.get(arr.size()-1)!=b[j])
                          {
                              arr.add(b[j]);
                          }
                          j++;
                  }
                  return arr;

**Link🔗:** <a href="https://www.codingninjas.com/studio/problems/sorted-array_6613259?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf">Find Unions</a>


## 8) Intersection of Two Arrays 🧩

- Given two integer arrays nums1 and nums2, return an array of their intersection. Each element in the result must be unique and you may return the result in any order.
- Input:  nums1 = [1,2,2,1], nums2 = [2,2]  Output: [2]

**Idea💡**
   -  For this, we can use **SET** data structure. Create 2 sets for each array [i.e. set filters & store the unique element from an array].  Eg. [1,2,2,1]=>[1,2] & [2,2]=>2
   -  After these, we have 2 unique sets, Now we have to find what are all the elements present in both sets, for that, we can use a predefined method,**retainAll**
   -  set1.retainAll(set2) => Element which are present in both set1 & set2 are kept in set1, other elements get deleted from the set1.
   -  Now we have intersected elements on the set, we can use the for-each loop to convert our set into the result array
   -  Code 👩🏻‍💻:

             Set<Integer> set1=new HashSet<>();
             Set<Integer> set2=new HashSet<>();
             for(int i=0;i<nums1.length;i++)
             {
                 set1.add(nums1[i]);
             }
             for(int j=0;j<nums2.length;j++)
             {
                 set2.add(nums2[j]);
             }
             set1.retainAll(set2);
             int[] result=new int[set1.size()];
             int p=0;
             for(int ele:set1)
             {
                 result[p++]=ele;
             }
             return result;

**Link🔗:** <a href="https://leetcode.com/problems/intersection-of-two-arrays/">Intersection of Two Arrays</a>


## 9) Missing Number 🔍

- Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.
- Input: nums = [3,0,1] Output: 2
 

**Approaches💡**

**1) Brute Force Approach:**

   -  By performing the linear search from 1 to num, We can able to find what number is missing in the array. 
   -  Code 👩🏻‍💻:

            int count=0;
            for(int i=0;i<=nums.length;i++)
           {
               count=0;
               for(int j=0;j<nums.length;j++)
               {
                   if(i==nums[j])
                   {
                       count++;
                   }
               }
               if(count==0)
               {
                   return i;
               }
           }
           return -1;
          }
      
**2) Better Approach:**

   -  By performing the hashing, i.e we can create an array of size(n+1), Iterate through our given array & update the value to 1
   -  After we hashed the entire array, we have to start iterating the hashed array if we find the value 0 i.e. the number is not there. We can return the index.
   -  Code 👩🏻‍💻:

           int[] hashArr=new int[nums.length+1];
           for(int i=0;i<nums.length;i++)
           {
               hashArr[nums[i]]++;
           }
           for(int j=0;j<hashArr.length;j++)
           {
               if(hashArr[j]==0)
               {
                   return j;
               }
           }
           return 0;

**2) Optimal Approach:**

   -  In simple, by adding the elements from 1 to n using n*(n+1)/2
   -  Adding all the elements from the given array. The difference between the total sum  & sum of n numbers will be the answer.
   -  
     
   -  Code 👩🏻‍💻:

           int sum=nums.length*(nums.length+1)/2;
           int count=0;
           for(int i=0;i<nums.length;i++)
           {
               count+=nums[i];
           }
           return sum-count;

**Link🔗:** <a href="https://leetcode.com/problems/missing-number/description/">Missing Number</a>





