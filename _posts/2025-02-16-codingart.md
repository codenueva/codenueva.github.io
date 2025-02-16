---
layout: post
title: Art Made With Code 10
date: 2025-02-16 10:47
category: artwithcode
author: codenueva
tags: [p5js,art,code,polygons]
summary: 
---

More polygons.

List of all sketches so far based on nested polygons.

{% for post in site.tags.polygons %}
<a href="{{post.url}}">{{ post.title }}</a>
{% endfor %}

---

```
// 09 Feb 2025
// codenueva
let colors;
let rmin, rmax,rstep;
let bl; 

function setup() {
    createCanvas(600, 600);
    colors = [color(227, 23, 10),color(169, 229, 187),color(252, 246, 177),color(247, 179, 43),color(45, 30, 47)]; 
    rmax = 250;   
    rmin = 10;
}

function draw() {
    noLoop();
    bl = random(colors);
    background(bl);
    design();   
}

function design(){
    push();
    translate(width/2,height/2);
    let n = int(random(3,9));
    rstep = random(4,12); 
    let shift = 0;
    let step = random(150,320);
    let shiftstep = 2*PI/step; 
    stroke(0,150);
    strokeWeight(max(rstep/4,3));
    for(let r = rmax; r > rmin; r-= rstep){
        let cl = random(colors);
        cl.setAlpha(220);
        fill(cl);
        beginShape();
        for(let a = 0; a < 2*PI; a+=2*PI/n){
            vertex(r*cos(a+shift),r*sin(a+shift));
        }
        endShape(CLOSE);
        shift += shiftstep;
    }   
    pop();
}
```

OUTPUT 

 <img src = "/assets/images/0010a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0010b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0010c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0010d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0010e.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0010f.png" alt="Grid 1" width="500" height="500"> 

  <img src = "/assets/images/0010g.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0010h.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0010i.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0010j.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0010k.png" alt="Grid 1" width="500" height="500"> 
