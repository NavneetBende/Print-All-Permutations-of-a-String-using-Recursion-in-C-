# Print-All-Permutations-of-a-String-using-Recursion-in-C-

All Permutation of a String using Recursion in C++
Here, in this page we will discuss the program to find all permutation of a string using recursion in C++ Programming Language. We are given with the string as an input and need to print all the permutation of the given input string. A permutation also called an “arrangement number” or “order,” is a rearrangement of the elements of an ordered list S into a one-to-one correspondence with S itself. A string of length n has n! permutation. 

Example :

Input : ABC
Output : ABC ACB BCA BAC CAB CBA
All Permutation of a String using Recursion in C++
Method 1(Using Recursion) :
 

Create a recursive function say permute(string s, int l, int r), and pass string along with starting index of the string and the ending index of the string.
Base condition will be if(l==r) then print the s.
Otherwise, run a loop from [l, r]
And, swap(s[l], s[i])
Call permute(s, l+1, r) function
And again swap(s[l], s[i]) to backtrack.
Permutation of given string
Code to print all permutation of a string using recursion in C++
Run
#include <bits/stdc++.h>
using namespace std;

//Recursive Function
void permute(string s, int l, int r)
{
   // Base case
   if (l == r)
     cout<<s<<" ";
   else
   {
      for (int i = l; i <= r; i++)
      {

          // Function to swap
          swap(s[l], s[i]);

          // Recursion called
          permute(s, l+1, r);

          //backtrack
          swap(s[l], s[i]);
        }
    }
}

// Driver Code
int main()
{
     string str = "ABC";
     int n = str.size();
     permute(str, 0, n-1);
     return 0;
}
Output :


ABC ACB BCA BAC CAB CBA
Related Pages
Finding Number of times x digit occurs in a given input
 
Finding number of integers which has exactly x divisors
 
Smallest element in an array

Power of a Number

Largest element in an array

Method 2(Using In-built Function) :
In this method we will use the next_permutation() function, that modifies a string so that it stores lexicographically next permutation. If current string is lexicographically largest, then next_permutation returns false.

Sort the string str.
Run a do while loop to print(str), and use next_permutation(str.begin(), str.end()) inside while condition.
Code in C++
Run
#include <bits/stdc++.h>
using namespace std;

//Function to print all permutations
void permute(string str)
{
   sort(str.begin(), str.end());

   do{
     cout<<str<<" ";
   }while(next_permutation(str.begin(), str.end()));
}

// Driver Code
int main()
{
  string str = "ABC";
  permute(str);
  return 0;
}
Output :


ABC ACB BCA BAC CAB CBA
