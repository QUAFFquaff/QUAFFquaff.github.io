---
layout: post
title: 05 Exception
date: 2020-08-27
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

# Exception
 
### compare C & C++

* C's handling of errors is to encode all errors (return codes), one error and one code. When programming, the programmer checks the return code that appears in the main calling function and gives the corresponding treatment. This method is cumbersome and irregular. What's more deadly is that this kind of "after-the-fact" mechanism will make all rescues too late.  
* C++ summarizes and abstracts all kinds of errors as *error types*, which are all handed over to throw; error handling is unified as catch calls. This establishes a unified specification for programmer programming, that is, operating agreement. More importantly, C++'s error handling mechanism is to *intercept* once an error occurs and do rescue processing. if it can be rescued, it will be saved, so it is *prevent trouble before it happens*.  

### a case of try catch
```C++ 
#include<iostream.h>
class DevidedByZero {
public:
     DevidedByZero (const char * p )；
     const char * description();
     // ...
    private:
      char * desp;
};
double Devide ( double a, double  b) {
	if( b== 0 ) 
        throw   DevidedByZero( “The divisor is 0.”);
	return a/b;
}
void main()
{	
    double x = 100,y = 20.5;
    try
	{
       cout<<"100 / 20.5="<<Devide(x,y)<<endl;
	}
    catch(const DevidedByZero & ex)
	{
       cerr<<ex.description();
     }
	cout<<"that is ok.\n";
}

```
