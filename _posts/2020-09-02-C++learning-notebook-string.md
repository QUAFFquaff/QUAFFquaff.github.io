---
layout: post
title: C++ String
date: 2020-08-30
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

Specially, this one is about string, I will keep update this article as soon as i met any valueable trick.  

# Some thing about string  


string::npos is the length of the string. means until the end of the string. like:  
tmpname.replace(idx+1,string::npos,suffix);

we can use substr and find to split a string as what we do in python.  
```C++
vector<string> split2(const string &str, const string &pattern)
{
    char * strc = new char[strlen(str.c_str())+1];
    strcpy(strc, str.c_str());   //string转换成C-string
    vector<string> res;
    char* temp = strtok(strc, pattern.c_str());
    while(temp != NULL)
    {
        res.push_back(string(temp));
        temp = strtok(NULL, pattern.c_str());
    }
    delete[] strc;
    return res;
}
```

or, we can use stringsteam to skip some charactors:  
```C++
vector<string> split3(const string &str, const char pattern)
{
    vector<string> res;
    stringstream input(str);   //读取str到字符串流中
    string temp;
    //使用getline函数从字符串流中读取,遇到分隔符时停止,和从cin中读取类似
    //注意,getline默认是可以读取空格的
    while(getline(input, temp, pattern))
    {
        res.push_back(temp);
    }
    return res;
}  
```  
