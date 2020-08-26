---
layout: post
title: C++ Sizeof
date: 2020-08-25
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

## Sizeof

* The size of the empty class is 1 byte.  
```C++
#include<iostream>
using namespace std;
class A{};
int main()
{
    cout<<sizeof(A)<<endl;
    return 0;
}
```
* In a class, the virtual function itself, member functions (including static and non-static) and static data members do not occupy the storage space of the class object.  
```C++
#include<iostream>
using namespace std;
class A
{
    public:
        char b;
        virtual void fun() {};
        static int c;
        static int d;
        static int f;
};

int main()
{
    /**
     * @brief 16  vptr指针=8
     */
    cout<<sizeof(A)<<endl; 
    return 0;
}
```
* For classes that contain virtual functions, no matter how many virtual functions there are, there is only one virtual pointer, the size of vptr.  
```C++
#include<iostream>
using namespace std;
class A{
    virtual void fun();
    virtual void fun1();
    virtual void fun2();
    virtual void fun3();
};
int main()
{
    cout<<sizeof(A)<<endl; // 8
    return 0;
}
```