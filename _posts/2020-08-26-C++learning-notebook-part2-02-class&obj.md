---
layout: post
title: 02 Class & Object
date: 2020-08-26
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

# constructor  

Two ways to define the constructor:  
```C++
Clock::Clock(int Hour, int Minute)
{
    m_Hour = Hour;	
    m_Minute = Minute;
}

// OR
Clock::Clock(int h, int m):m_Hour(h), m_Minute(m)
{
}
```  
### Copy constructor  
>"When using an existing object to initialize another new object of the same kind, call the copy constructor."    

```C++
class   foo{
public:
    foo(string string1,int num,double* ptr);
    foo(const foo &f);
    void get_name(){
        cout<<this->string1<<endl;
    }
private:
    string string1;
    int num;
    double* douptr;

};
foo::foo(string string2,int num, double* ptr) :
    string1(string2),num(num),douptr(ptr){
    cout<<"this is :"<<string1<<endl;
}

foo::foo(const foo &f){
    string1 = f.string1;
}


int   main(){
    foo   f("class Name",1,NULL);
    foo   f2(f);
    f2.get_name();
}

```
* When an object of the class is used to initialize another object of the class, the system automatically calls the copy constructor to realize copy initialization.  
* If the formal parameter of a function is a class object, when the function is called, the formal parameter is initialized with the actual parameter, and the system automatically calls the copy constructor.  
```C++
void fun1(Clock c)
{   
    cout<<c.GetHour()<<endl;
} 
int main()
{
    Clock c1(1,2);
    fun1(c1);
    return 0;
}
```
* When the return value of the function is a class object, the system automatically calls the copy constructor.  
  

**Vital**
> If one class has constructor but no copy constructor, compiler will make up for a default copy constructor to complete the copy of the object when needed;
> Conversely, when a class writes a copy constructor with out explicitly writing a constructor, the compiler will report an error when object create statement.

### Object copy prohibited
```C++
class NoCopy
{ 
public:
      NoCopy( int ){…}
      //... 
private:
      NoCopy( const NoCopy & ) {…}   // copy ctor
      NoCopy &operator =( const NoCopy & ) {…} //operator =
}; 
```
# destructor  
Acctually this is not that much to say about destructor, sometimes we can overwrite destructor and call it.  but program will run it automaticly anyways.
```C++
class App  {//	App *pa = new App; //	delete pa;
public:
    App()  {	cout<<"running contructor\n "<<endl;  }
    ~App()  {	cout<<"running destructor"<<endl;    }
};
int  main()  {
    cout<<"This is main function"<<endl;
    App app;
    cout<<&app<<endl;
    app.~App();
    cout<<"main function end"<<endl;
    cout<<&app<<endl;
}
```

