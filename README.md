# C++-Course
Gives Information about C++ and OOPS Concept from VIT (VIT BHOPAL UNIVERSITY)

### Course Instructor:- Dr. Shreyasi Mam and Dr. L. Sathish Kumar 

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
#### Sample code for user defined function
```
#include <iostream>

using namespace std;
int calcSum(int,int);
int main()
{
cout << "Hello world!" << endl;
int x,y,z;
cout << "enter two integers: ";
cin>>x>>y;
z=calcSum(x,y);
cout << "The sum is" << z <<endl;
return 0;
}

int calcSum(int a, int b)
{
int s;
s=a+b;
return s;
}
```
#### Vector Example
```
#include<iostream>
#include<vector>
using namespace std;

int main()
{
vector<int> a;
for(int i=0;i<9;i++)
{
a.push_back(i+1);
}
cout<<"value at 0: "<<a.at(0);
cout<<"Size: "<<a.size();
cout<<"Capacity: "<<a.capacity();
}
```
#### Copy constructor
```
#include<iostream>
using namespace std;
class Test
{
private:
int objectID;
string message;
public:
Test(int id,string msg)
{
objectID=id;
message=msg;
}
Test(const Test &obj)
{
cout<<"In copy constructor"<<endl;
objectID=obj.objectID;
message=obj.message;
}

void display()
{
cout<<"Object ID:"<<objectID<<"\t"<<message<<endl;
}
};

int main()
{
Test s1(2,"Welcome");
Test s2=s1;
cout<<"First object"<<endl;
s1.display();
cout<<"Second object"<<endl;
s2.display();
}
```
#### Destructor
```
#include<iostream>
using namespace std;
class Test
{
private:
int objectID;
string message;
public:
Test(int id,string msg)
{
objectID=id;
message=msg;
cout<<"Object ID:"<<objectID<<"\t"<<message<<endl;
}

~Test()
{
cout<<"Destructor runs for object:"<<objectID<<endl;
}
};
Test s(1,"Global object");

int main()
{
Test s1(2,"Local object");
}
```

#### Friend function
```
#include<iostream>
using namespace std;
class Test
{
friend void setID(Test &,int);
private:
int objectID;
public:
Test(int id)
{
objectID=id;
}
void display()
{
cout<<"Object ID:"<<objectID<<endl;
}
};

void setID(Test &t,int a)
{
t.objectID=a;
}
int main()
{
Test s1(2);
s1.display();
setID(s1,3);
s1.display();

}
```
#### Exception - example 
```
#include<iostream>
#include<exception>
using namespace std;
//creating a function that throws an exception
void throwException()
{
try
{
cout<<"\nFunction throwException throws an exception";
//the function throws an exception
throw exception();
}
//this catch block catches the exception
catch(exception &)
{
cout<<"\nException handled in function";
//here the exception is rethrown
throw;
}
}
int main()
{
try
{
cout<<"\nmain invokes function throwException";
throwException();
cout<<"unreachable";
}
//this catch block catches the exception thrown from the function
catch(exception &)
{
cout<<"\nException handled in main";
}

cout<<"\nProgram continues after main";
}
```

#### Exception handling - stack unwinding

```
#include<iostream>
#include<stdexcept>
//stack unwinding - When an exception is not caught in a particular scope,
//the function call stack is unwound and an attempt is made to catch the
//exception in the next outer try…catch block.

using namespace std;
void function3()
{
cout<<"\nInside function 3";
throw runtime_error("runtime error in function 3");
}
void function2()
{
cout<<"\nCalling function 3 for f2";
function3();
cout<<"\nback to f2";

}
void function1()
{
cout<<"\nCalling function 2 from f1";
function2();
cout<<"\nback to f1";

}
int main()
{
try
{
function1();
}
catch(runtime_error &e)
{
//e.what() prints the error message that we have sent as an argument
cout<<"\nException occurred: "<<e.what()<<endl;
cout<<"Exception handled in main";
}
}
```

# Disclaimer

* Use only for Educational Purpose
* Open source LICENSED
