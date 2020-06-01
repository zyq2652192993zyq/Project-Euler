> # Project Euler: Problem 3 - Largest prime factor

The prime factors of 13195 are 5, 7, 13 and 29.

What is the largest prime factor of the number 600851475143 ?

---

```c++
#include <iostream>

using namespace std;

const int inf = 0x0FFFFFFF;

long long LargestPrimeFactor(long long num)
{
    long long maxFactor = -inf;
    for (long long i = 2; i <= num; ++i){
        while (num != i){
            if (num % i == 0){
                maxFactor = max(maxFactor, i);
                num /= i;
            }
            else break;
        }
    }
    maxFactor = max(maxFactor, num);
    

    return maxFactor;
}

int main()
{
    int result = LargestPrimeFactor(600851475143);

    cout << result << endl;

    return 0;
}
```

注意一点，600851475143赋给`int`会溢出，所以用`long long`类型