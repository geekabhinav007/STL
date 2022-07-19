[Home](./tutorial.html){: .btn .fs-10 .mr-4}

### Pair

Pair is used to combine together two values that may be of different data types. Pair provides a way to store two heterogeneous objects as a single unit. It is basically used if we want to store tuples. The pair container is a simple container defined in <utility> header consisting of two data elements or objects.
**Syntax**
  ```c++
  pair < datatype 1st object , datatype 2nd object > pairName;
  ```
 Example
  ```c++
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // defining a pair
    pair<int, char> PAIR1;
  
    // we can refer using pairName.first and similary for second element pairName .second
    // first part of the pair
    PAIR1.first = 1;

    // second part of the pair
    PAIR1.second = 'A';
    cout << PAIR1.first << " "<<PAIR1.second<<endl;
  
    // pair of pair
    pair<int, pair<int, int>> nestedPair = {1, {102, 33}};
    // Array of pairs
    pair<int, int> arr[] = { {1, 2},
                             {12, 13},
                             {333, 233} };
    // we can print pair element of nested pair and array of pairs like that
    cout<<nestedPair.first<<" "<< nestedPair.second.first<<" "<<nestedPair.second.second<<endl;
    cout<<arr[0].first<<" "<<arr[2].second<<endl;
    return 0;
}
  ```
 Output
```
1 A
1 102 33
1 233
```
