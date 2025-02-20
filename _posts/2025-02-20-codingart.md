---
layout: post
title: Art Made With Code 13
date: 2025-02-20 11:53
category: artwithcode
author: codenueva
tags: [p5js,art,code,patterns]
summary: 
---


Patterns in rows. 

```
// 15 Feb 2025
// codenueva

let rows;
let cols; 
let margin; // outer margin for the entire sketch
let rmargin; // margin for each cell
let colors; //palette

function setup() {
    createCanvas(900, 900);
    rows = 18;
    cols = 1;
    margin = int(random(20,60));
    rmargin = int(random(2,10));
    colors = [color(226, 141, 0),color(125, 8, 63),color(177, 0, 0),color(200, 217, 218),color(108, 2, 17)];
    
}

function draw() {
    
    noLoop();
    background(255); 
    let rectWidth = (width-2*margin)/cols;
    let rectHeight = (height-2*margin)/rows;
    
    
    for (let j = 0; j < rows; j++) {
    // Calculate position for each rectangle
        push();
        let x =  margin;
        let y =  margin + j*rectHeight ;
        noStroke();
        let cl = random(colors);
        fill(cl);
        rect(x,y,rectWidth,rectHeight);
        divRow(x,y,rectWidth,rectHeight);
        pop();
    }
    
}


function divRow(x,y,w,h){
    let nc = 18;
    let nw = w/nc; 
    for(let i = 0; i < nc; i += 1){
        push();
        translate(x+i*nw,y);
        let sp = 4;
        stroke(5);
        strokeWeight(0);
        let t = int(0.5*nw/sp);
        for(let j = 0; j < t; j += 1){
            cl = random(colors);
            fill(cl);
            beginShape();
            vertex(j*sp,h);
            vertex(0.5*nw,2*h*sp*j/nw+sp);
            vertex(nw-j*sp,h);
            endShape(CLOSE);
        }
        pop();
    }

}
```

---

OUTPUT 

 <img src = "/assets/images/0013a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0013b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0013c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0013d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0013e.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0013f.png" alt="Grid 1" width="500" height="500"> 

<img src = "/assets/images/0013g.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0013h.png" alt="Grid 1" width="500" height="500"> 