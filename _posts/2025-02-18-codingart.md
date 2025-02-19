---
layout: post
title: Art Made With Code 11
date: 2025-02-18 18:21
category: artwithcode
author: codenueva
tags: [p5js,art,code,recursion,grid]
summary: 
---

A grid made by recursive division. Uses the very famous [Mondrian color scheme](https://color.adobe.com/tijl---Piet-Mondrian-color-theme-6225068/)

```
// 10 Feb 2025
// codenueva
let colors;
let rmin, rmax,rstep;
let bl; 

function setup() {
    createCanvas(600, 600);
    colors = [color(243, 243, 243),color(245, 15, 15),color(250, 227, 23),color(13, 127, 190),color(0, 0, 0)];
    rmax = 250;   
    rmin = 10;
}

function draw() {
    noLoop();
    bl = random(colors);
    background(255);
    divideGrid(10,10,width-20,height-20,15,3);
}

function divideGrid(x,y,w,h,level,s){
   
    design(x,y,w,h,s);
    
    if(level < 0 || w < s || h < s){
        return;
    }


    let ch = random();

    // divide along width 
    if (ch > 0.5){
        let k = random(0.3,0.7);
        divideGrid(x,y,k*w,h,level-1,s);
        divideGrid(x+k*w,y,(1-k)*w,h,level-1,s); 
    }
    else{
        let k = random(0.3,0.7);
        divideGrid(x,y,w,k*h,level-1,s);
        divideGrid(x,y+k*h,w,(1-k)*h,level-1,s);
    }
}

function design(x,y,w,h,s){
    let cl = random(colors);
    cl.setAlpha(255);
    strokeWeight(min(0.25*s,1));
    stroke(0);
    fill(cl);
    rect(x,y,w,h);
}

```

---

OUTPUT 

 <img src = "/assets/images/0011a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0011b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0011c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0011d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0011e.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0011f.png" alt="Grid 1" width="500" height="500"> 

<img src = "/assets/images/0011g.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0011h.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0011i.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0011j.png" alt="Grid 1" width="500" height="500"> 

 
