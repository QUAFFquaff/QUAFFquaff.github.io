---
layout: post
title: From C to C++
date: 2020-08-26
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

## C++ is a legend

> C: Process-oriented programming model  
> Object-Based (C++) 
> Object-Oriented (C++)
> Template (C++)

**Use <iostream> instead of scanf or printf**  
**Experience the use of objects brings you a lot of convenience**  

Things about reference:  
```C++
int ival = 1024; 
int &refVal = ival;     // ok: refVal refers to ival 
int &refVal2;       // error: a reference must be initialized 
int &refVal3 = 10;   // error: initializer must be an object 
```
How to declare a reference to an array
```C++
int a[10];
int &ra[10] = a; //error, its not one reference to an array but one reference array.
int(&ra)[10] = a ; 
```
### dynamic allocate memory
in C we use malloc\free
but in C++, we recommond new\delete
 >  Date *pmc = new Date(5, 22, 2012);  
 > delete pmc;  

 **Vital**: Do not delete non-dynamic memory, its unstable.
 for example:
 ```C++
int i = 10;
int *p = &i;
delete p;
```




