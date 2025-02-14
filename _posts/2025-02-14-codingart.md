---
layout: post
title: Art Made With Code 8
date: 2025-02-14 21:39
category: artwithcode
author: codenueva
tags: [p5js,art,code,polygons]
summary: 
---

More patterns from nested polygons. 

List of all sketches so far based on nested polygons.

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
    let n = 4;
    // change rn for diff patterns 
    let rn = 8;
    let k = random(0.4,0.7);
    stroke(0,100);
    strokeWeight(max(rstep/4,2));
    for(let r = rmax; r > rmin; r-= rstep){
        let cl = random(colors);
        cl.setAlpha(220);
        fill(cl);
        for(let ra = 0; ra < 2*PI; ra+= 2*PI/rn ){
            beginShape();
            for(let a = 0; a < 2*PI; a+=2*PI/n){
                vertex(r*cos(a+ra),r*sin(a+ra));
                vertex(k*r*cos(a+ra+(PI/n)),k*r*sin(a+ra+(PI/n)));
            }
            endShape(CLOSE);
        }
        
    }   
    pop();
}
```

OUTPUT 

 <img src = "/assets/images/0008a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0008e.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008f.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008g.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008h.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008i.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008j.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0008k.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008l.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0008m.png" alt="Grid 1" width="500" height="500"> 