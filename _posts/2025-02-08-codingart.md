---
layout: post
title: Art Made With Code 6
date: 2025-02-08 07:09
category: artwithcode
author: codenueva
tags: [p5js,art,code,polygons]
summary: 
---

Few more variations of [nested](https://codenueva.github.io/artwithcode/2025/02/01/codingart.html) [polygons](https://codenueva.github.io/artwithcode/2025/02/07/codingart.html).

```
// 08 Feb 2025
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
    let rn = 18;
    stroke(0,10);
    strokeWeight(max(rstep/3,3));
    for(let r = rmax; r > rmin; r-= rstep){
        let cl = random(colors);
        cl.setAlpha(200);
        fill(cl);
        for(let ra = 0; ra < 2*PI; ra+= 2*PI/rn ){
            beginShape();
            for(let a = 0; a < 2*PI; a+=2*PI/n){
                vertex(r*cos(a+ra),r*sin(a+ra));
            }
            endShape(CLOSE);
        }
        
    }   
    pop();
}
```
OUTPUT 

 <img src = "/assets/images/0006a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0006b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0006c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0006d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0006e.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0006f.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0006g.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0006h.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0006i.png" alt="Grid 1" width="500" height="500"> 
  
 <img src = "/assets/images/0006j.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0006k.png" alt="Grid 1" width="500" height="500"> 