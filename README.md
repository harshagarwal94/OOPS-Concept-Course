# C++-Course
Gives Information about C++ and OOPS Concept from VIT (VIT BHOPAL UNIVERSITY)

### Course Instructor:- Dr. Shreyasi Mam

# Course Overview

```


(!)


Introduction to object-oriented approach: 


Why object-oriented programming?
Characteristics of object oriented language: classes and objects - encapsulation-
data abstraction- inheritance - polymorphism - Merits and Demerits of object
oriented programming. UML- class diagram of OOP - Inline function – default
argument function- Exception handling(Standard) - reference: independent
reference – function returning reference – pass by reference



(2)


Classes and objects: 


Definition of classes – access specifier – class versus
structure – constructor – destructor – copy constructor and its importance – array
of objects – dynamic objects- friend function-friend class – container class


(3)


Polymorphism and Inheritance:


Polymorphism-compile time polymorphism – function overloading – operator
overloading - . Inheritance-types of inheritance- constructors and destructors in
inheritance – constraints of multiple inheritance-Abstract base class – pure virtual
functions- run time polymorphism-function overriding.



(4)


Exception handling and Templates


Exception handling(user-defined exception)- Function template , Class template –
Template with inheritance , STL – Container, Algorithm, Iterator -vector, list,
stack, map



(5)


IOstreams and Files


IOstreams, Manipulators- overloading Inserters(<<) and Extractors(>>)-Sequential
and Random files – writing and reading objects into/from files – binary files


```

#### Login functionality
```
#include <iostream>

using namespace std;

int main()
{
const string username="admin",password="admin";
string userid,pass;
for(int attempt=1;attempt<=3;attempt++)
{
cout<<"Please enter user id";
cin>>userid;
cout<<"Please enter password";
cin>>pass;
if(userid.compare(username)==0 && pass.compare(password)==0)
{
cout<<"Welcome";
break;
}
else if(attempt<3)
{
cout<<"Incorrect userid/password! Please enter again\n";
}
if(attempt==3)
{
cout<<"Your account is locked";
}
}
return 0;
}
```



# Disclaimer

* Use only for Educational Purpose
* MIT LICENSED
