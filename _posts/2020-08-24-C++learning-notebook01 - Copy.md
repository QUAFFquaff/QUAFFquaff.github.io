---
layout: post
title: C++ Const
date: 2020-07-11
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

## Const

> "Use const whenever possible"

### 1. impact of const 
* Define constant 
* type check 
* can not be modified   

### 2. pointer & const 
```C++
const char* p;              //data is const, data can not be changed
char* const p;              //pointer is const, 
const char* const p;        //both data and pointer are const
```
const stays at the left of *, modify data，means pointer point to constant;  
const stays at the right side of *，modify pointer，means pointer is constant.  
  
### 3. const in functions  
 
```C++
void func(const int var); // input varible can not be changed 
void func(int *const var); // pointer can not be changed
void StringCopy(char *dst, const char *src); // input a pointer which point to a const varible
void func(const A &a) // varible is reference, in order to protect and Increase efficiency
```

#### 4. const obj default is intern  
Ordinary variables are set to extern by default, but const It must be explicitly specified as extern in the file.  
>Ordinary variables can use from differenet files  


 ```C++
 // file1.cpp
int ext
// file2.cpp
#include<iostream>
extern int ext;
int main(){
    std::cout<<(ext+10)<<std::endl;
}
```

> const varible must clearify  
```C++
//extern_file1.cpp
extern const int ext=12;
//extern_file2.cpp
#include<iostream>
extern const int ext;
int main(){
    std::cout<<ext<<std::endl;
}
```

### 5. use const in class  
If one function will not modify any data, then it should be set as const.
  
const object can only run const function;
non-const object can run all.
```C++
//apple.cpp
class Apple
{
private:
    int people[100];
public:
    Apple(int i); 
    const int apple_number;
    void take(int num) const;
    int add(int num);
    int add(int num) const;
    int getCount() const;

};
//main.cpp
#include<iostream>
#include"apple.cpp"
using namespace std;

Apple::Apple(int i):apple_number(i)
{

}
int Apple::add(int num){
    cout<<" add func "<<num<<endl;
    take(num);
}
int Apple::add(int num) const{
    cout<<"const add func "<<num<<endl;
    take(num);
}
void Apple::take(int num) const
{
    cout<<"take func "<<num<<endl;
}
int Apple::getCount() const
{
    take(1);
    add(1); //error
    return apple_number;
}

int main(){
    Apple a(2);
    cout<<a.getCount()<<endl;
    a.add(10);
    const Apple b(3);
    b.add(100);
    return 0;
}
//compile： g++ -o main main.cpp apple.cpp
//result
take func 1
2
take func 10
take func 100
```
