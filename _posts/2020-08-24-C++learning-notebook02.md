---
layout: post
title: C++ This pointer
date: 2020-08-25
tags: C++_Things
---

This artical is about how I learning the C++. It contains the steps I go through and the problems I met. Also there will be some test cases attached onto the page.

## This

> "As a python user,*this* in C++ is similar to *self* in python."

### 1. Some special use 

* If a non-static function will return the object itself, it will use: return *this  
* When the parameter is the same as the member variable name, such as this->n = n (cannot be written as n = n)

Looks like nothing special. I'll add more if meet any interesting *this*.