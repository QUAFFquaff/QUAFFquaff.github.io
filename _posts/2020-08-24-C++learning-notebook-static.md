---
layout: post
title: C++ Static
date: 2020-07-11
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

## Static

> "The space for static variables is only allocated once"


### 1. General use

```C++
#include <iostream> 
#include <string> 
using namespace std; 

void demo() 
{ 
    // static variable 
    static int count = 0; 
    cout << count << " "; 

    // value is updated and 
    // will be carried to next 
    // function calls 
    count++; 
} 

int main() 
{ 
    for (int i=0; i<5; i++)  
        demo(); 
    return 0; 
}

```   
in this canse, the out put will be :  
0 1 2 3 4   
The static varible just declear once.

And static varibles live entire lifecycle. so lets look at this example:
```C++
#include<iostream> 
using namespace std; 

class Apple 
{ 
    int i; 
    public: 
        Apple() 
        { 
            i = 0; 
            cout << "Inside Constructor\n"; 
        } 
        ~Apple() 
        { 
            cout << "Inside Destructor\n"; 
        } 
}; 

int main() 
{ 
    int x = 0; 
    if (x==0) 
    { 
        static Apple obj; 
    } 
    cout << "End of main\n"; 
} 
```
The output would be 
>Inside Constructor  
>End of main  
>Inside Destructo  

Thats crazzy cause if we dont define that obj as static, the output should be:
>Inside Constructor  
>Inside Destructo  
>End of main  
normally program first involes Destructor then end itself. But static is different.  

### static function

We can use a static function without instantiation.