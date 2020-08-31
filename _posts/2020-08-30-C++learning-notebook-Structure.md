---
layout: post
title: C++ structure STL 
date: 2020-08-30
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

# What is STL  
STL , standard template  library, is a kind of container/algorithm, its the template of structure.
 
# Vector

```C++
#include <vector>
//build vector object
vector<int> v1;
vector<int> v2(10);
//init 10 value of 8.6 in one vector
vector<double> v3(10,8.6);
```
visit  

```C++  
//derictly 
v2[2] = 3;
// use iterator
cout<<*(v2.begin()+2)<<endl;
```
### Iterate  
```C++
//use index
for(int i=0;i<V3.size();i++){
  cout<<v3[i]<<'';
}
//use iterator
for(vector<int>::iterator it=v2.begin();it!=v2.end();it++){
  vout<<*it<<end;
```   
### insert
```C++
//tail extend
v.push_back(9);
//certain place
v.insert(v.begin()+2,1);
v.insert(v.end(),3);
```
### delete
```C++
v.erase(v.begin()+1);
//delete a area
v.erase(v.begin()+2,v.begin()+5);
//all
v.clear();
```
### sort
```C++
//increase
sort(v.begin(),v.end());
//decrease
sort(v.begin(),v.end(),greater<int>());
```
### others
```C++
   //元素反向排列
    reverse(v.begin(),v.end());

    //获取向量大小（元素个数）
    v.size()

	//向量是否为空
	v.empty()
```  

# **Map**  
### build  
```C++
map<string,double> m;
```
### insert & visit
```C++
m["jack"] = 98.5;
cout<<m["Jack"]<<endl;
```
### iterate
```C++
map<string,double>::iterator it;
for(it=m.begin();!it!+m..end()lit++)
cout<<(*it).first<<":"<<(*it).second<<endl;
```
### delete
```C++
    //通过键值删除
    m.erase("Jack");
    
    //清空
    m.clear();
```
### find
usually we can use key to get value, but some times we can also use m.find()  
* use find() function find key location.   

```C++
    map<string,double>::iterator it;
    it=m.find("Jack");
    cout<<(*it).first<<":"<<(*it).second<<endl;
    
    //equals to
    
    cout<<"Jack"<<":"<<m["Jack"]<<endl;
    
```  
* use count() function judge whether a key is appear or not.   

```C++
    if(m.count("Jack"))
        cout<<"FOUND"<<endl;
    else
        cout<<"NOT FOUND"<<endl;
	
	//equals to
	
    if(m["Jack"])
        cout<<"FOUND"<<endl;
    else
        cout<<"NOT FOUND"<<endl;
```

# **Set**  
>Sets are containers that store unique elements following a specific order.  

### initilization
```C++
set<int> s1;    
//-----------------//
struct comp
{
   bool operator() ( const int& lhs,  const int& rhs )
   {
       return lhs > rhs ;
   }
};
set<int, comp> s2;   //降序

//--------------//


struct Node
{
    int x;
    int y;
    friend bool operator < (Node a, Node b)//结构体排序(重载<操作符)：
    {
        return a.x<b.x; //按照x升序
    }
};

set<Node> s3;
```

### insert and visit  
```C++
s1.insert(5);
s2.insert(Node{8,5});

//must use iterator to visit
cout<<*s1.begin()<<endl;//first element
cout<<*(--s1.end())<<endl;//last one
```
### iterator
```C++
set<int>::iterator itl
for(it=s1.begin()lit!=s1.end();it++)
cout<<*it<<endl;
```
### delete
```C++
//delete value is 5
s1.erase(5);
//delete first one 
s1.erase(s1.begin));
//clear
s1.clear();
```
### find
```C++
if(s1.find(5)!=s1.end())
        cout<<"FOUND"<<endl;
    else
        cout<<"NOT FOUND"<<endl;
```