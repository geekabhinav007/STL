## Welcome to STL tutorial.

The Standard Template Library (STL) is a set of C++ template classes to provide common programming data structures and functions such as lists, stacks, arrays, etc. It is a library of container classes, algorithms, and iterators. It is a generalized library and so, its components are parameterized.
### STL has 4 components:
- Algorithms
- Containers
- Functions
- Iterators

### Let's Begin

When the program is using STL, it should `#include` the appropriate standard headers. For most containers the title of standard header matches the name of the container, and no extension is required. For example, if you are going to use stack, just add the following line at the beginning of your program:
```
#include<stack>
```
Container types (and algorithms, functors and all STL as well) are defined not in global namespace, but in special namespace called “std.” Add the following line after your includes and before the code begin:

```
using namespace std;
```

Another important thing to remember is that the type of a container is the template parameter. Template parameters are specified with the **‘<’/’>’** “brackets” in code. For example:

```
vector < int > N;
```

When making nested constructions, make sure that the “brackets” are not directly following one another – leave a blank between them.
```
vector < vector < int > > CorrectDefinition;
vector < vector < int >> WrongDefinition; // Wrong: compiler may be confused by ‘operator > >’
```
### VECTOR


