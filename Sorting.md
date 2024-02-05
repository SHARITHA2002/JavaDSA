## Sorting

1) Selection Sort
2) Bubble sort
3) Insertion Sort


## 1) Selection Sort

- Select the minimum & swap it with that index

PseudoCode💡

  - First, we have to iterate through the  entire array, hence we need a loop
  - Second, for comparing other elements, we need an inner loop. from [i to arr. length]
  - OK, now initialize the first index has a minimum element
  - Inside the inner loop, check if any other element is lesser than mini, if it is set it is mini.
  - Then, swap the first position with that mini element.
  - The above steps go until all the elements are sorted.

Code👩‍💻

       for(int i=0;i<arr.length;i++)
       {
         int mini=i;
         for(int j=i;j<arr.length;j++)
         {
             if(arr[j]<arr[mini])
             {
               mini=j;
             }
         }
         //Swap the minimum element index with the mini index
         int temp=arr[mini];
         arr[mini=arr[i];
         arr[i]=temp;
       }
       
Time Complexity ⏰ 

  n+(n-1)+(n-2)+... => O(n<sup>2</sup>)


## 2) Bubble Sort

 - Check for adjacents, if adjacent is greater, then swap


PseudoCode💡:

- Start an outer loop from o to arr. length -1
- Next iterate an inner loop from 0 to arr.length-i-1
- Check if arr[i]>arr[i+1],if it is then swap arr[i] && arr[i+1]

Code 👩‍💻

        for(int i=0;i<arr.length-1;i++)
        {
          for(int j=0;j<arr.length-i-1;j++)
          {
            if(arr[j]>arr[j+1])
            {
              int temp=arr[j];
              arr[j]=arr[j+1];
              arr[j+1]=temp;
              didswap=1;
            }
          }
        }

Time Complexity ⏰

  Worst case : O(n<sup>2</sup>)
  Best Case  : O(n), that means given arr is sorted 
