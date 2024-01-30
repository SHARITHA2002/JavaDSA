## Hashing#️⃣

   - Hashing in terms, Combinations of the steps, pre-storing & fetching.
    
**1) Pre-storing**
    
   - Pre-storing, pre-calculating the information [i.e., about the element of the array] before answering the queries.

**2) Fetching:**

   - We will select each query [i.e. the number and for the query, we will just fetch the value of hash[number]]  
   -Return it instead of running a ‘for loop’ every time.

## Types of Hashing

**1) Number Hashing**

  - Problem: To count the number of occurrences of each element in an array.
  - Solution: Using Hashing, the Steps are as follows,
    
      1)  Create a new array for hashing with the size they given as  the max element
      2)  iterate through the given array, for every value, increment the value in the new hash array =>Pre-Storing
      3)  now, we can get the each no of occurrence from the end of the iteration =>Fetching
  - But the max array size is for INT arr it is 10<sup>6</sup>, When we declare outside the class it can be 10<sup>7</sup>

  **2) Character Hashing**
   - Problem: To count the number of occurrences of each character in an array.
   - Solution: Using Hashing, the Steps are as follows,
     
     1) Character hashing in this case, we need a hash array of size 26 for alphabets & 256 for all characters
     2) Iterate through the given array, for every value, increment the value in the new hash array => Prestoring
     3) Use the formula to fetch the occurrence corresponding value for 26 arr size = given character – ‘a’,if it is 256,no formula needed,we can directly access it =>fetching
