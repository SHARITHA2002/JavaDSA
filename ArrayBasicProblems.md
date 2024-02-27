## Arrays Basic Problems

## Find the Largest element in an array

**Brute Force Approach:**
- Sort the array in an ascending order using any of the sorting algo & return the last index (arr[n-1])
- Time complexity  : O(n log n) Space Complexity : O(1)

**Optimal Approach:**
- set a variable with an Integer.MIN_VALUE & start iterating the loop & compare it with every value of the arr , if any of the values is > than Max , replace max with the current value of arr.
- Time complexity  : O(log n) Space Complexity : O(1)

**Code**

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
