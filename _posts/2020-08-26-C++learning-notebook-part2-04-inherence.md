---
layout: post
title: 04 Inheritance & polymorphism
date: 2020-08-26
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

# Inherit

# Polymorphism  

```C++
class Clock
{
public:
    void ShowInstruction(){
        cout<<"can show time, sales $150!"<<endl;
    }
private:
    int m_Hour;
    int m_Minute;
};
class Media_Clock : public Clock
{
public:
    void ShowInstruction(){
        cout<<"can play music watch, sales $200~"<<endl;
    }
    …
};
int main() {
    Media_Clock MediaClk;
    Clock *pClk = &MediaClk;
    MediaClk.ShowInstruction();
    pClk->ShowInstruction();
    return 0;
}
```
This case tells us we shouldn't redefine a non-virtual function, otherwise it will cause problems.


Some other cases:
```C++
class Base
{
public:
    void f() {cout<<"Base::f\n";}
    virtual void g() {cout<<"Base::g\n";}
protected:
private:
};
class Derived:public Base  {
public:
    void f() {cout<<“Derived::f\n”;}	
    void g() {cout<<"Derived::g\n";}
    void h() {cout<<"Derived::h\n";}
protected:
private:
};
```
case one :   
```C++
    Base b;
    Derived d;
    
    b.f();//Base:: f() 
    b.g();//Base::g()
    b.h();//error
    
    d.f();//Derived::f()
    d.g();//Derived::g()
    d.h();//Derived::h()
```  

```C++
    Base b;
    Derived d;
     
    Base *pb = &b;
    pb->f();//Base::f
    pb->g();//Base::g
    pb->h();//error
    
    Base *pb1 = &d;
    pb1->f();//Base::f
    pb1->g();Derived::g
    pb1->h();//error

```

