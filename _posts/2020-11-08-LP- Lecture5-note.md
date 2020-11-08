---
layout: post
title: L5: Duality 
date: 2020-11-06
tags: Linear Optimization
---

# 5 Duality  
## Resource Allocation  
Recall resource allocation problem m=2, n=3  
max c1x1 + c2x2 + c3x3  
s.t. a11x1 + a12x2 + a13x3 <=b1  
    a21x1 + a22x2 + a23x3<=b  
            x1,x2,x3>=0  

    cj: profit per unit of pro  
    bi: units of raw material on hand  
    aij: unit of raw raw material i needed to produce one unit on product j.  


## Closing shop  
If we produce one unit less of product J, then we freasi  
-aij units of material 1  
-aij units of material 2  -------- raw materials  

selling these raw materials for y1&y2 dollars per unit yields a1jy1+a2jy2 dollars  
only interested in selling if the amount exceeds out profit.   
    a2jyi + a2jy2 >= cj, j = 1,2,3  
A buyer who wants to purchase the entire inventory lices to minimize cost  .  

min b1y1 + b2y2  
s.t. a1y1 + a2y2>=c1  
    a2y2+a22y2>=c2  
    a13y3+a32y2>= c3   

## Duality   
Every problem  
max sum(cjxj  
s.t. sum( aijxj<= bi ,
has a dual   
min sum(biyi)  
st. sum(yiaij)>=cj

## Dual Simplex Pivot Rules  

Applied if dual is feasible  

1) all coefficients of the non-basic varibales in the primal objective function must be non-zero    
2) select departing variable as the basic variable whose coefficient in the dictionary is most negative.  
3) pick the entering variable by scanning across this row of the dictionary and comparing rotios of coefficients in the objective row.

take an example