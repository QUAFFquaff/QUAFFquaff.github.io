---
layout: post
title: C++ Inline
date: 2020-08-25
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

## Inline

Some times we should not use inline, when:  
* code is too long in function.(it will cost much more memory)  
* if there are loops in function. ( run the code in function cost more time than call function.)

### Can Virtual function Inline  ?

Yes, But when the virtual function is polymorphic, it cannot be inlined.  


### Conclusion  
Inline is kind of useless, sometimes even we write *inline* there, the compiler think we are fool and it will not inline.

### **special problem**
```C++
#define MAX(a, b) ((a)>(b))?(a):(b)


int main()
{
    int i = 10;
    int j =8;
    MAX(++i,j);
    cout<<i;      // 11

//    int i = 10;
//    int j = 8;
//    MAX(++i,j);
}
```
the output is 12
((++i)>j) ? (++i) : (j);