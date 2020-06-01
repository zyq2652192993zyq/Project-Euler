> # Project Euler Problem 4 - Largest palindrome product

A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is 9009 = 91 × 99.

Find the largest palindrome made from the product of two 3-digit numbers.

---

```c++
#include <iostream>
#include <string>

using namespace std;

bool isPalindrome(int x)
{
    string s = to_string(x);
    int end = s.size() - 1, start = 0;
    
    while(start <= end){
        if (s[start] == s[end]){
            ++start;
            --end;
        }
        else{
            return false;
        }
    }
    
    return true;
}

int main()
{
    bool flag = false;
   for (int i = 999; i >= 900; --i){
       for (int j = i; j >= 900; --j){
           if (isPalindrome(i * j)){
               flag = true;
               cout << i << " * " << j << " = " << i * j << endl;
               break;
           }
       }
       if (flag) break;
   }
   
   return 0;
}
```

```shell
# run result
993 * 913 = 906609
```

