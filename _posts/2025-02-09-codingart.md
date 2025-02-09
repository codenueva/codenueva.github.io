---
layout: post
title: Art Made With Code 7
date: 2025-02-09 11:20
category: artwithcode
author: codenueva
tags: [p5js,art,code,polygons]
summary: 
---

Continuing with nested polygons.

Here is a list of all sketches so far based on nested polygons.

{% for post in site.tags.polygons %}
<a href="{{post.url}}">{{ post.title }}</a>
{% endfor %}

---

```
// 08 Feb 2025
// codenueva
let colors;
let rmin, rmax,rstep;

function setup() {
    createCanvas(600, 600);
    colors = [color(208, 0, 0),color(255, 186, 8),color(63, 136, 197),color(255),
              color(19, 111, 99),color(138, 201, 38),color(3, 43, 67)];
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
    let n = 3;
    let rn = 6;
    stroke(0,0);
    //strokeWeight(max(rstep/3,3));
    for(let r = rmax; r > rmin; r-= rstep){
        let cl = random(colors);
        cl.setAlpha(230);
        fill(cl);
        for(let ra = 0; ra < 2*PI; ra+= 2*PI/rn ){
            beginShape();
            for(let a = 0; a < 2*PI; a+=2*PI/n){
                curveVertex(r*cos(a+ra),r*sin(a+ra));
            }
            endShape(CLOSE);
        }
        
    }   
    pop();
}
```
OUTPUT 

 <img src = "/assets/images/0007a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0007b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0007c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0007d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0007e.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0007f.png" alt="Grid 1" width="500" height="500"> 

 