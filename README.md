MOORES VOTING ALGORITHM.
 int Findcandidate(int a[],int size) {   // This function will return the most repeated element in array.
   int maj_index=0,count=1;
  for(int i=1;i<size;i++){
    if(a[maj_index]==a[i])
         count ++;
  else
         count--;
  if(count==0){
     maj_index=i;
     count=1; }
    }                      //for loop closed.
    return a[maj_index];
    }
    
    
    
    JUGGLING ALGORITHM.
      void ArrayRotation(int a[],int gcd) {    // This function will rotate few  parts of whole array by a given length.
        for(int i=0;i<gcd;i++){
         int temp=a[i];
         int j=i;
         while(1) {     // we are using this loop to reach the end of the array by jumping  d distance each time .
           int k=j+ d;
                if(k>=n)     // This line is to terminate the loop , the moment we reach at the end of array.
                  k=k-n;
                if(k==i)
                   break;
                a[j]=a[k];
                  j=k;
                 }     // while loop ended.
                 a[j]=temp;
                 }       // For loop ended.
                 }       // Function ended.
             
             
             
