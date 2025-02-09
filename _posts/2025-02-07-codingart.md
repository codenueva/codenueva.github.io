---
layout: post
title: Art Made With Code 5
date: 2025-02-07 19:49
category: artwithcode
author: codenueva
tags: [p5js,art,code,polygons]
summary: 
---

What was supposed to be a daily effort has now turned into a weekly affair :(

This sketch is a continuation of [sketch 4](https://codenueva.github.io/artwithcode/2025/02/01/codingart.html) based on nested polygons.

```
// 07 Feb 2025
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
    stroke(0,150);
    strokeWeight(max(rstep/3,3));
    //strokeWeight(4);
    for(let r = rmax; r > rmin; r-= rstep){
        let cl = random(colors);
        cl.setAlpha(220);
        fill(cl);
        beginShape();
        for(let a = 0; a < 2*PI; a+=2*PI/n){
            vertex(r*cos(a),r*sin(a));
        }
        endShape(CLOSE);
        beginShape();
        for(let a = 0; a < 2*PI; a+=2*PI/n){
            vertex(r*cos(a+(PI/4)),r*sin(a+(PI/4)));
        }
        endShape(CLOSE);
    }   
    pop();
}
```

OUTPUT 

 <img src = "/assets/images/0005a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0005b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0005c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0005d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0005e.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0005f.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0005g.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0005h.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0005i.png" alt="Grid 1" width="500" height="500"> 
 
