## Welcome to STL tutorial.

The Standard Template Library (STL) is a set of C++ template classes to provide common programming data structures and functions such as lists, stacks, arrays, etc. It is a library of container classes, algorithms, and iterators. It is a generalized library and so, its components are parameterized. C++ STL is mainly divide into four parts as followings:
### STL has 4 components:
- Algorithms
- Containers
- Functions
- Iterators

### Let's Begin

When the program is using STL, it should `#include` the appropriate standard headers. For most containers the title of standard header matches the name of the container, and no extension is required. For example, if you are going to use stack, just add the following line at the beginning of your program:

```c++ 
#include<stack>
```
Container types (and algorithms, functors and all STL as well) are defined not in global namespace, but in special namespace called “std.” Add the following line after your includes and before the code begin:

```c++ 
using namespace std;
```

Another important thing to remember is that the type of a container is the template parameter. Template parameters are specified with the **‘<’/’>’** “brackets” in code. For example:

```c++ 
vector < int > N;
```

When making nested constructions, make sure that the “brackets” are not directly following one another – leave a blank between them.
```c++ 
vector < vector < int > > CorrectDefinition;
vector < vector < int >> WrongDefinition; // Wrong: compiler may be confused by ‘operator > >’
```
```c++
#include<bits/stdc++.h>
```
This above code is haeder file to include all the libraries present in `C++`, so we don't bother to add each libarary sepretely because of this we can code more efficiently and fast without having multiple line for inclusion of each library or header file sepretely.

### Container

A C++ container is a holder object that stores a collection of other objects (its elements). They are implemented as class templates, which allows a great flexibility in the types supported as elements.

The container manages the storage space for its elements and provides member functions to access them, either directly or through iterators (reference objects with similar properties to pointers).

Containers replicate structures very commonly used in programming: **dynamic arrays (vector)**, **queues (queue)**, **stacks (stack)**, **heaps (priority_queue)**, **linked lists (list)**, **trees (set)**, **associative arrays (map)** e.t.c

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
### VECTOR (Dynamic array)
  
 Vectors are sequence containers representing arrays that can change in size.

Just like arrays, vectors use contiguous storage locations for their elements, which means that their elements can also be accessed using offsets on regular pointers to its elements, and just as efficiently as in arrays. But unlike arrays, their size can change dynamically, with their storage being handled automatically by the container.

**Syntax**
```c++
  vector< any datatype> vectorName;
```
**Example**
  
```c++
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int> v;
    v.push_back(45);
    v.emplace_back(89); 
    // emplace_back is faster and more efficient than push_back
    // https://stackoverflow.com/questions/4303513/push-back-vs-emplace-back
    for (int i = 0; i < 2; i++)
    {
        cout << v[i] << " ";
    }
    cout << endl;

    // vector of pair datatype
    vector<pair<int, int>> vp;
    vp.push_back({1,2});   
    // push_back rquires currly braces to push pair element in a vector.
    vp.emplace_back(4,5); 
    // emplace_back dont required currly braces to push a pair value in vector

    // declare vector of some size or some values filled already in it.

    // vector of size 6 having 0 or any garbage value (Depends on compiler).
    vector<int> vec(6); 
    // vector of size 6 with default value 142 in it.
    vector<int> vect(6,142); 
    // copy vector vect to v2
    vector<int> v2(vect); 
    return 0;
}
  ```
 **Output**
  ```
  45 89
  ```
We can increase the size of vector easily even after declearing the size of a vector example `vector<int> v[5]` we can easily insert 6th element in the `vector v` by appling `push_back` method on it.
#### Accessing Elements in a vector
```c++
#include <bits/stdc++.h>
using namespace std;
int main()
{
    vector<int> v1 = {10,20,35,89};
    // Accessing Elements in a vector
    // we can access elements in vector as a similar fashion like array.
    cout<<v1[0]<<endl;
    // we can also access elements ny the use of iterator


    return 0;
}
```
  **Output**
  ```
  10
  ```




