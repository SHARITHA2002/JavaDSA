
## Searching 🔍

- Searching is nothing but finding a given target element in a particular space i.e an array

     a) Linear Search
  
     b) Binary Search
    

**1) Linear search:**

  - Linear Search is defined as a sequential search algorithm that starts at one end and goes through each element of a list until the desired element is found
  - Otherwise, the search continues till the end of the data set.
  - ⏰ Time complexity : O(n)

   Code 👩‍💻

          int[] arr={1,2,4,5,7,8};
          int target=7;
          for(int i=0;i<arr.length;i++)
          {
              if(arr[i]==target)
              {
                  System.out.println(i); // Returning the position of the target Element
              }
          }

**2) Binary Search:**

- Binary Search is  a  kind of searching algorithm used in a sorted array by repeatedly dividing the search interval in half.
- The idea of binary search is to use the information that the array is sorted and reduce the time complexity to O(log N).
- ⏰Time Complexity: O(log N)

Code 👩‍💻
          
            int[] arr={1,2,3,4,5,6,7,8,9,10};
            int target=7;
            System.out.println(binarySearch(arr,target));

            public static int binarySearch(int[] arr,target)
            {
                int left=0;
                int right=arr.length-1;
                while(left<=right)
                {
                    int mid=left+(right-left)/2;
                    if(target>arr[mid])
                    {
                        left=mid+1;
                    }
                    else if(target<arr[mid])
                    {
                        right=mid-1;
                    }
                    else
                    {
                        return mid;
                    }
                }
                return -1;
            }


Binary Search -Interview Questions: 👔

   - https://github.com/SHARITHA2002/JavaDSA/blob/main/BinarySearch-InterviewQuestions.md

     
