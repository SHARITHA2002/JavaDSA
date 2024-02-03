## Pattern Printing

         55555
         54444
         54333
         54322
         54321

- Approach💡
  1)Separate the pattern into 2 part

        5       5555
        54       444
        543       33
        5432       2
        54321
  
- Code:

          int n=5;
  
          for(int i=1;i<=n;i++)
          {
            //First Half
            for(int j=1;j<=i;j++)
            {
                System.out.print(n-j+1);
            }
  
            //Second Half
            for(int k=1;k<=n-1;k++)
            {
              System.out.print(n-i+1);
            }
  
            System.out.println("");
        }

- Reference:
    https://www.atnyla.com/program/program-to-print-number-pattern-pre-55555-54444-54333-54322-54321-pre-/1/762#google_vignette
  
