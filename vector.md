[Home](./tutorial.html){: .btn .fs-10 .mr-4}
### VECTOR (Dynamic array)
  
 Vectors are sequence containers representing arrays that can change in size.

Just like arrays, vectors use contiguous storage locations for their elements, which means that their elements can also be accessed using offsets on regular pointers to its elements, and just as efficiently as in arrays. But unlike arrays, their size can change dynamically, with their storage being handled automatically by the container.

**Syntax**
```c++
  vector<object_type> vectorName;
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
To understand the difference between emplace_back and push_back follow the following link on stackoverflow ([emplace_back vs push_back](https://stackoverflow.com/questions/4303513/push-back-vs-emplace-back))
  
We can increase the size of vector easily even after declearing the size of a vector example `vector<int> v[5]` we can easily insert 6th element in the `vector v` by appling `push_back` method on it.
#### Iterator
Iterators are used to point at the **memory addresses** of STL containers. They are primarily used in sequences of numbers, characters etc. They reduce the complexity and execution time of the program.
An iterator is any object that, pointing to some element in a range of elements (such as an array or a container), has the ability to iterate through the elements of that range using a set of operators (with at least the increment (++) and dereference (*) operators).

The most obvious form of iterator is a pointer: A pointer can point to elements in an array, and can iterate through them using the increment operator (++). But other kinds of iterators are possible.
**Syntax**
  ```c++
    vector<int>::iterator it = v1.begin(); 
 ```
#### Accessing Elements in a vector
```c++
#include <bits/stdc++.h>
using namespace std;
int main()
{
     vector<int> v1 = {10, 20, 35, 89};
    // Accessing Elements in a vector
    // we can access elements in vector as a similar fashion like array.
    cout << "Accessing Vector using index(element at zeroth index): " << v1[0] << endl;
    cout << "Accessing Vector using at method(element at zeroth index): " << v1.at(0) << endl;
    cout << "Accessing Vector end element using back method(element at last index): " << v1.back() << endl;
    // we can also access elements ny the use of iterator
    // Declearition of iterator
    vector<int>::iterator it = v1.begin();
    cout << "type :- " << typeid(it).name() << "\nAddress:- " << &it << endl;
    cout << "Value at the address where iterator it is pointing " << *(it) << endl;
    vector<int>::iterator it2 = v1.end();
    cout << "Value at the address where iterator it2 is pointing " << *(it2) << endl;
    /*printed zero because the address in not the
    part of our vector so it's value may be garbage or zero depending on the compiler.
    */

    /*
    Above result conclude that the int data type have 2 byte storage in memory,
    also we have it pointing to the begining of the vector and it is pointing
    to the end of the vector.
     */

    // Printing all the elements of vector
    cout << "Elements of vector V1 are:- ";
    for (vector<int>::iterator itr = v1.begin(); itr != v1.end(); itr++)
    {
        cout << *(itr) << " ";
    }
    cout << endl;

    // using auto
    cout << "Elements of vector V1 are:- ";
    for (auto itr1 = v1.begin(); itr1 != v1.end(); itr1++)
    {
        cout << *(itr1) << " ";
    }
    cout << endl;

    // using foreach loop
    cout << "Elements of vector V1 are:- ";
    for (auto itr1: v1)
    {
        cout << itr1 << " ";
    }
    cout << endl;
    return 0;
}
```
  **Output**
  ```
Accessing Vector using index(element at zeroth index): 10
Accessing Vector using at method(element at zeroth index): 10
Accessing Vector end element using back method(element at last index): 89
type :- N9__gnu_cxx17__normal_iteratorIPiSt6vectorIiSaIiEEEE
Address:- 0x7fffffffdad8
Value at the address where iterator it is pointing 10
Value at the address where iterator it2 is pointing 0
Elements of vector V1 are:- 10 20 35 89 
Elements of vector V1 are:- 10 20 35 89 
Elements of vector V1 are:- 10 20 35 89 
  ```
**The auto keyword is simply asking the compiler to deduce the type of the variable from the initialization.**

#### Operations on vector
  
1. begin() ??? it returns an iterator pointing to the first element of the vector.
```c++
  auto iterator = itr;
  itr = v1.begin();
  ```
2. end() ??? it returns an iterator pointing to the element theoretically after the last element of the vector.
```c++
  auto iterator = itr;
  itr = v1.end();
  ```
3. push_back() ??? it accepts a parameter and insert the element passed in the parameter in the vectors, the element is inserted at the end.
```c++
  vector<int> v1;
  v1.push_back(5);
  v1.push_back(2);
  ```
4. insert() ??? it is used to insert an element at a specified position.
```c++
  auto it= v1.begin();
  v1.insert(it,5); //inserting 5 at the beginning
  ```
5. erase() ??? it is used to delete a specific element
```c++
  vector<int> v1;
  auto it= v1.begin();
  v1.erase(it);// erasing the first element
  ```
6. pop_back() ??? it deletes the last element and returns it to the calling function.
```c++
  v1.pop_back();
  ```
7. front() ??? it returns a reference to the first element of the vector.
```c++
  v1.front();
  ```
8. back() ??? it returns a reference to the last element of the vector.
```c++
  v1.back();
  ```
9. clear() ??? deletes all the elements from the vector.
```c++
  v1.clear();
  ```
10. empty() ??? to check if the vector is empty or not.
```c++
  v1.empty();
  ```
11. size() ??? returns the size of the vector
```c++
  v1.size();
  ```
**Example**
  
  ```c++
  
  #include <bits/stdc++.h>
  using namespace std;

  int main()
  {
      vector<int> v;

      for (int i = 0; i < 10; i++)
      {
          v.push_back(i); // inserting elements in the vector
      }

      cout << "The elements in the vector: ";
      for (auto it = v.begin(); it != v.end(); it++)
          cout << *it << " ";

      cout << "\nThe front element of the vector: " << v.front();
      cout << "\nThe last element of the vector: " << v.back();
      cout << "\nThe size of the vector: " << v.size();
      cout << "\nDeleting element from the end: " << v[v.size() - 1];
      v.pop_back();

      cout << "\nPrinting the vector after removing the last element:" << endl;
      for (int i = 0; i < v.size(); i++)
          cout << v[i] << " ";

      cout << "\nInserting 5 at the beginning:" << endl;
      v.insert(v.begin(), 5);
      cout << "The first element is: " << v[0] << endl;
      cout << "Erasing the first element" << endl;
      v.erase(v.begin());
      cout << "Now the first element is: " << v[0] << endl;

      if (v.empty())
          cout << "\nvector is empty";
      else
          cout << "\nvector is not empty" << endl;

      v.clear();
      cout << "Size of the vector after clearing the vector: " << v.size() << endl;
      ;
      return 0;
  }
  ```
  
**Output**
  
```
The elements in the vector: 0 1 2 3 4 5 6 7 8 9 
The front element of the vector: 0
The last element of the vector: 9
The size of the vector: 10
Deleting element from the end: 9
Printing the vector after removing the last element:
0 1 2 3 4 5 6 7 8 
Inserting 5 at the beginning:
The first element is: 5
Erasing the first element
Now the first element is: 0
vector is not empty
Size of the vector after clearing the vector: 0
```
  
**Other Functions:**

- **cbegin()** ??? it refers to the first element of the vector.
- **cend()** ??? it refers to the theoretical element after the last element of the vector.
- **rbegin()** ??? it points to the last element of the vector.
- **rend()** ??? it points to the theoretical element before the first element of the vector.
- **crbegin()** ??? it refers to the last element of the vector.
- **crend()** ??? it refers to the theoretical element before the first element of the vector.
- **max_size()** ??? returns the maximum size the vector can hold.
- **capacity()** ??? it returns the current capacity of the vector.

