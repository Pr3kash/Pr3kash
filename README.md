<1 >    MOORES VOTING ALGORITHM.

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
    
    
    
 <2 >     JUGGLING ALGORITHM.
    
      void ArrayRotation(int a[],int gcd) {    // This function will rotate few  parts of whole array by a given length.
        for(int i=0;i<gcd;i++){
         int temp=a[i];
         int j=i;
         while(1) {     // we are using this loop to reach the end of the array by jumping  d  distance each time .
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
             
             
          
          
<3 >    MOST FREQUENT ELEMENT    (METHOD 1)
 
      int  MostfrequentElement(vector<int>v1)
      int x,max_count=0,index;
   sort( arr.begin() , arr.end() );
for(int i=0;i<arr.size();i++){
    x=count( arr.begin(),arr.end(),arr[i] );
    
    
    
    
       if(x>max_count){
        index=i;
        max_count=x;
    }
}
  return arr[index];
  }

                                 // USING MAP TO FIND FREQUENT ELEMENT  (METHOD 2) //
 
   int MostfrequentElement(vector<int> arr) {
    int max=0,ans;
    map<int,int>m;
    for(int i=0;i<arr.size();i++){
        m[arr[i]]++;
    }
    map<int, int>::iterator itr;
   for(itr= m.begin(); itr!=m.end(); itr++){
       if(itr->second>max){
           max=itr->second;
           ans=itr->first;
       }
    }
    return ans;
}
          
          
  <4 >   LEAP YEAR CODE IN ONE LINE 
 
   if( ((year%4) &&(year%100))|| ((year%4)&&(year%400)) ){
                  cout<<" Leap Year";
                         }
          
          
 <5 >   
       
    An arcade game player wants to climb to the top of the leaderboard and track their ranking. The game uses Dense Ranking, so its leaderboard works like this:
The player with the highest score is ranked number  on the leaderboard.
Players who have equal scores receive the same ranking number, and the next player(s) receive the immediately following ranking number.
Example    ,  ranked=[100,90,90,80,60] (Descending order)
              player=[70,72,80,105,120]  (Ascending order)
          output = [4,4,3,1,1]
          
      ---code---
       
  vector<int> climbingLeaderboard (vector<int> ranked, vector<int> player) {
     int rank[200000 +1];
    for (int i = 0; i < ranked.size(); i++) {   // Loop for finding rank array based on index//
        if (i == 0) {
            rank[i] = 1;
        }
        else {
            if (ranked[i] == ranked[i-1]) {
                rank[i] = rank[i - 1];
            }
            else {
                rank[i] = rank[i - 1] + 1;
            }
        }
    }     //Loop for rank array closed//
     int  points=(ranked.size())-1;
vector<int >v;

for(int j=0;j<player.size();j++){
    
    while(points>=0 && player[j]>ranked[points]){
        points--;
    }
    if(points==-1){
        v.push_back(1);
    }
    else if(player[j]==ranked[points]){
        v.push_back(rank[points]);
    }
    else if(player[j]<ranked[points]){
        v.push_back(rank[points]+1);
    }
}
return v;
} // Function closed//
                                       
          
          
          
 <6 >   Railway Time Conversion code.
       
       string timeConversion(string s) {
   if(s[8]=='A'){
        if(s[0]=='1'&& s[1]=='2'){
            s[0]='0';
            s[1]='0';
        }
   }
   else{
       if(! (s[0]=='1'&&s[1]=='2') ){
           s[0]+=1;
           s[1]+=2;
       }
   }
 string s1 =s.substr(0,8);
   
   return s1;
}
          
          
          
  
       
       
       
       <7 >    EXTRA LONG FACTORIAL.
             
             
             
             void extraLongFactorials(int n) {
    int carry = 0;
    vector <int> arr(200, 0);
    arr[0] = 1; //Initial product = 1

    int k = 0; //Current size of the number stored in arr

    for(int i = 2; i <= n; i++) {
        for(int j = 0;j <= k; j++) {
            arr[j] = arr[j] * i + carry;
            carry = arr[j] / 10;
            arr[j] = arr[j] % 10;
        }
        while(carry) { //Propogate the remaining carry to higher order digits
            k++;
            arr[k] = carry % 10;
            carry /= 10;
        }   
    }
    for(int i = k; i >= 0; i--) {
        cout << arr[i];
    }
    cout<<endl;
}
             
             
             
             
             
             
             
            < 8 >  Maximal subset S' of a set S ( Distinct integer ) where sum of any two  no is Not divisible by a number k.
                  
                  
int nonDivisibleSubset(int k, vector<int> s) {
 map<int>m;
int ans=0,c=0,j;
for(int a=0;a<s.size();a++){
    m[s[a]%k]++;
}
if(m[0]>0){
    ans++;
}
if (k%2==0) {
    for(int i=1;i<k;i++){
        j=k-i;
        if(i==k/2){
            (m[i]>0)?ans++:c=1;
            break;
        }
        else{
            ans=ans+max(m[i],m[j]);
        }
    }
}
else {
    for(int i=1;i<k;i++){
        j=k-i;
        if(j<i){
           break;
        }
        else{
            ans=(ans+max(m[i],m[j]) );
            }
    }
}
return ans;
}
             
       
       
                  
          < 9 >   Return the string which is the  Next largest string of a given string (if arranged in Lexicographical order).
          
          
          
 string biggerIsGreater(string w) {
    string s0;
    int  n=w.length(),c=0;
    char arr[n+1];
    strcpy(arr, w.c_str());                        // COPYING A COMPLETE STRING IN CHAR ARRAY.
    while (next_permutation(arr, arr+ n)){                // PRE DEFINE FUNCTION -- next_permutation -- It returns next greater string of current string passed.
         string s2(arr,arr+n);                     // CHAR ARRAY TO STRING.
         s0=s2;
         c++;
         break;
     }
     if(c==0){
        return "no answer";
     }
     else{
         return s0;
     }
}
          
          
          
          
          
          
          
          
          
          
          
          
          
          
          
          
