---
layout: post
title: Art Made With Code 4
date: 2025-02-01 13:41
category: artwithcode
author: codenueva
tags: [p5js,art,code]
summary: 
---

Could not keep up the streak. Things have been chaotic. Todya's sketch is a simple one involving nested polygons. 

```
// 01 Feb 2025
// codenueva
let colors;
let rmin, rmax,rstep;

function setup() {
    createCanvas(600, 600);
    colors = [color(249, 200, 14),color(248, 102, 36),color(234, 53, 70),
              color(102, 46, 155),color(67, 188, 205)];     
    rmin = 10; 
    rmax = 250; 
    rstep = int(random(4,20));   
}

function draw() {
    noLoop();
    background(random(colors));
    design();   
}

function design(){
    push();
    translate(width/2,height/2);
    let n = 4;
    stroke(0,190);
    strokeWeight(max(rstep/3,3));
    for(let r = rmax; r > rmin; r-= rstep){
        let cl = random(colors);
        cl.setAlpha(230);
        fill(cl);
        beginShape();
        for(let a = 0; a < 2*PI; a+=2*PI/n){
            vertex(r*cos(a),r*sin(a));
        }
        endShape(CLOSE);
    }   
    pop();
}
```
OUTPUT 

 <img src = "/assets/images/0004a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0004b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0004c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0004d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0004e.png" alt="Grid 1" width="500" height="500"> 