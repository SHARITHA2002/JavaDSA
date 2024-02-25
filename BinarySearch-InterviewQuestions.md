## Binary Search -Interview Questions

## 1) Find the floor of a number
   
-  The greatest number which is **less than(Floor)or equal** to the target number.
-  Input: nums = [1,2,4,5,15,18,19], target = 7 : Output: 3 [5]
- The key here is to return the **end**. 
  
**Code 👩‍💻 :**
              
          int[] arr={1,2,4,5,15,18,19};
  	      int target=7;
	      System.out.println("Floor of a number:"+binarySearch(arr,target));
               
            	public static int binarySearch(int[] arr,int target)
            	{
            	    int start=0;
            	    int end= arr.length-1;
            	    while(start<=end)
            	    {
            	        int mid=start+(end-start)/2;
            	        if(arr[mid]==target)
            	        {
            	            return mid;
            	        }
            	        else if(target>arr[mid])
            	        {
            	            start=mid+1;
            	        }
            	        else
            	        {
            	            end=mid-1;
            	        }
            	    }
            	    
            	    return end;
            	}
       
## 2) Find the ceil of a number

- The smallest number is **greater than(Ceil)or equal**  to the target number.
- Input: nums = [1,4,5,14,16,18,20,25,29,30], target = 15 : Output: nums[4] 16
- The key here is to return to the **start**. 
       
**Code 👩‍💻 :**
              
              int[] arr={1,4,5,14,16,18,20,25,29,30};
  	          int target=15;
              //Output: 16
	            System.out.println("Ceil of a number:"+binarySearch(arr,target));
               
            	public static int binarySearch(int[] arr,int target)
            	{
            	    int start=0;
            	    int end= arr.length-1;
            	    while(start<=end)
            	    {
            	        int mid=start+(end-start)/2;
            	        if(arr[mid]==target)
            	        {
            	            return mid;
            	        }
            	        else if(target>arr[mid])
            	        {
            	            start=mid+1;
            	        }
            	        else
            	        {
            	            end=mid-1;
            	        }
            	    }
            	    
            	    return start;


## 3) Find the Smallest Letter Greater Than the Target :

   Input: letters = ["c", "f", "j"], target = "a"
   
   Output: "c"
   
   Explanation: The smallest character that is lexicographically greater than 'a in letters is 'c'.

**Idea 💡:**

 - From greater than the target itself, we can find that they ask for ceil. If it is ceil, then we should return **start**
 - Two things to be noted are that, 
 - The question is **greater than** not greater than or equal to, hence don't check the (target==letters[mid])equal condition.
 - Second thing, If such a character does not exist, return the first character in letters.

 Example: letters =["p", "q", "r"] target="s", return "p".

 - For this case, we can use "letters[start%letters.length]" =>letters[2%3]=> return letters[0] {First letter}

**Link:🔗** https://leetcode.com/problems/find-smallest-letter-greater-than-target/ 
   
## 5)  Find the First and Last Position of the Element in the Sorted Array

1. Input: nums = [5,7,7,8,8,10], target = 8 : Output: [3,4]

2. Input: nums = [5,7,7,8,8,10], target = 6 : Output: [-1,-1]

**Idea💡**

 1) BruteForce Approach

    - Having a 2 loop, the First loop traverses from the start, if it finds the target stores the position in the result[0] & breaks the loop.
    - The other loop start traverses from the end to the end, if it finds the target stores the position in the result[1] & breaks the loop.
    - Time complexity ⌛: O(n)
      
2) Optimal Approach

    - We have to find two things (first position, last position), hence we can run a binary search 2 times, 1st time for finding 1st position,2nd time for finding the last position
    - If the target is found there may be a possibility the answer is also on the left & right.
    - Once the potential answer is found check, For 1st position, check the left side of the target if the number is present [start=0,end=mid-1]
    - For the 2nd position, check the right side of the target if the number is present [start=mid+1,end=arr.length-1]
    -  Time complexity ⌛: O(log n)

**Link:🔗** https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/description/

## 6) Find the position of an element in a sorted array of infinite numbers

**Idea💡**
 - In normal Bsearch, we can find the length i.e) arr. length, But they said that An arr is infinite, We can't able to use the arr. length
 - So by reverse thinking the Bsearch, We start searching chunk by chunk from the size of 2 [0,1], if a target is found return the target otherwise double the size of the chunk
 - Conditions, when double the chunk size, is as long as our target is greater than the arr[end].

**Code👩🏻‍💻**

	   public static void main(String[] args)
           {
			int[] arr={3, 5, 7, 9, 10, 90,100, 130, 140, 160, 170};
			int target=10;
			System.out.print(findans(arr,target));
	   }
		public static int findans(int[] arr,int target)
		{
		    int start=0;
                    int end=1;
		    while(target>arr[end])
			{
			    start=end+1;
			    int newStart=end+1;
			    end=(newStart*2)+1;
			}
			return binarySearch(arr,target,start,end);
		}
		public static int binarySearch(int[] arr,int target,int start,int end)
		{
		    while(start<=end)
		    {
		        int mid=start+(end-start)/2;
		        if(target>arr[mid])
		        {
		            start=mid+1;
		        }
		        else if(target<arr[mid])
		        {
		            end=mid-1;
		        }
		        else
		        {
		            return mid;
		        }
		   }
		   
		   return -1;
		}

**Link:🔗** https://www.geeksforgeeks.org/find-position-element-sorted-array-infinite-numbers/


## 7) Peak Index in a Mountain Array

**Mountain array / Bitonic Array:**

  - A mountain array is an array of length at least 3 with elements strictly increasing from starting till index i, and then strictly decreasing from index i to last index.
  - Input: arr = [0,10,5,2] Output: 1

 **Idea💡**
 - There will be no target, so we have to check with the adjacents based on certain conditions
 - 1st condition would be, if arr[mid]>arr[mid+1]: we are in the descending part Hence , end=mid;
 - Or else we are in the descending part , then start=mid+1;
 - The loop will iterate until a single element, hence when the start & end are at the same position, the return any one of them [start/end]

 **Code👩🏻‍💻**

 	public int peakIndexInMountainArray(int[] arr) 
    {
        int start=0;
        int end=arr.length-1;

        while(start<end)
        {
            int mid=start+(end-start)/2;
            if(arr[mid]>arr[mid+1])
            {
                end=mid;
            }
            else
            {
                start=mid+1;
            }
        }

        if(start==end)
        {
            return start;
        }
        return -1;
    }


**Link:🔗** https://leetcode.com/problems/peak-index-in-a-mountain-array/description/



