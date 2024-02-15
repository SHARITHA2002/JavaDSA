## Binary Search -Interview Questions

1) Find the floor of a number

     - arr[]={1,2,4,5,15,18,19};
     - target=7 : ans => 5 [15,18,19]
     -  The greatest number which is less than or equal to the target number.
  
Logic 💡: 

  - It searches for target element 15, throughout the array
  - The case here is the floor of a number, at last [15,18,19] are there,
    - while(start<=end) & mid=15, target<mid => end=mid-1 , then [5,15] end:5 start:15
  
Code 👩‍💻 :
              
              int[] arr={1,4,5,14,16,18,20,25,29,30};
  	          int target=15;
              //Output: 14
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
       
2) Find the ceil of a number

     - arr[]={1,2,4,5,15,18};
     - target=7 : ans => 15,[1,2,4,5]
     - The smallest number which is greater than or equal to the target number.
       
Code 👩‍💻 :
              
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
