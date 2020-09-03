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