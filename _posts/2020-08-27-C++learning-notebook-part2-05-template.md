---
layout: post
title: 04 Template
date: 2020-08-27
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

# Template
 
>template <typename sth>
 
This is one example of teamplate:
```C++
template <typename T>
int compare( const T& v1, const T& v2)
{
	if (v1 < v2) return -1;
      if (v2 < v1) return 1;
      return 0;
}
int main ()
{
    cout << compare(1, 0) << endl;
    string s1 = "hi", s2 = "world";
    cout << compare(s1, s2) << endl;
    return 0;
}

```
In this case compiler build two *compare function*, one is   
```C++
int compare( const int &v1, const int &v2)
```
and the other is 
```C++
int compare( const string &v1, const string &v2)
```  
A bug of compiler:  
```C++
# include <iostream.h>
template<typename T, int size>
int asz( T A[size] )
{
    cout<<size<<endl;
    cout<<A<<endl;
	for(int i=0;i<size;++i)
	      cout<<A[i]<<"  ";
	cout<<endl;	
	return size;
}

void main() 
{   int  b[3]={0,1,2},a[5]={3,4,5,6,7};
    cout<<b<<endl;
    cout<<a<<endl;
    const int sz1 = asz<int,5>(a);
    const int sz2 = asz<int,3>(b);
//  const int sz2 = asz<double,30>(b);
	cout<<"sz1 : "<<sz1<<endl;
	cout<<"sz2 : "<<sz2<<endl;
}
```  
The ouput of size is 3, 
Since the array is declared as int b[3], a[5]; so the realization must use int (if other types are used, it will be compiled incorrectly). And because the typename T is of the same type twice, the compiler only presents one function, and makes its second modulus parameter int size get the value. This value is the value given in the last time, so it is obviously 5 The elements have become three. It can be seen that for multiple arrays, if their data types are the same, it is difficult to take care of it using explicit realization.
