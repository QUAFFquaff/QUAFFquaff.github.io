---
layout: post
title: L6  Matrix Notation
date: 2020-11-06
tags: Linear_Optimization
---


# 6 Matrix Notation  

## Notation  
constraints :   
Ax = b - > Bxb + Nxn = b   
matrix B : m*m is invertible   
since basic variables in a dictionary can be written as independent linearr combo's of non-basic variables assuming linearly dependent constrains are combined.  

Express \( x_B \) in terms of \( x_N \):

1. 
\[
x_B = B^{-1}b - B^{-1}N x_N
\]

2. 
\[
\eta = c_B^T x_B + c_N^T x_N = c_B^T B^{-1} b - \text{(expression to be completed)}
\]

DIctionary in matrix notation  

## Verification  

## Dual Notation

## What was gained?  
1. A notation for carrying out proofs.  
2. NUmerical implementions of simplex method avoid explicitly calculationg $B^{-1}N$  

Although B&N are typically sparse, $B{-1}$ is not.  
Better solve $BX_B = b - NX_N$ efficiently and directly   

## Neg. Trans. Property  

Primal:  
max $$C^Tx$$  
s.t. $$Ax<=b$$  

Dual:  
min