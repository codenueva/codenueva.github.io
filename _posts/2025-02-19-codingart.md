---
layout: post
title: Art Made With Code 12
date: 2025-02-19 12:59
category: artwithcode
author: codenueva
tags: [p5js,art,code,patterns]
summary: 
---

Patterns in a grid. 

```
// 14 Feb 2025
// codenueva

let rows;
let cols; 
let margin; // outer margin for the entire sketch
let rmargin; // margin for each cell
let colors; //palette

function setup() {
    createCanvas(900, 900);
    rows = int(random(8,12));
    cols = rows;
    margin = int(random(20,60));
    rmargin = int(random(2,10));
    colors = [color(226, 141, 0),color(125, 8, 63),color(177, 0, 0),color(200, 217, 218),color(108, 2, 17)];
    
}

function draw() {
    
    noLoop();
    background(255); 
    let rectWidth = (width-2*margin)/cols;
    let rectHeight = (height-2*margin)/rows;
    
    for (let i = 0; i < cols; i++) {
        for (let j = 0; j < rows; j++) {
        // Calculate position for each rectangle
        push();
        let x =  margin + i * rectWidth ;
        let y =  margin + j * rectHeight ;
        translate(x + rectWidth/2,y +  rectHeight/2); 
        design(rectWidth, rectHeight);
        pop();
        }
    }
}

function design(w,h){
   
    drawingContext.save();
    rectMode(CENTER); 
    let cl = random(colors);
    cl.setAlpha(255);
    fill(cl);
    noStroke();
    rect(0, 0, w,h);
    drawingContext.clip();
    push();
    let n = 4;
    let rstep = 12;
    let i = 0; 
    for(let r = 6*w; r > 0.01*w; r-= rstep){
        let cl = random(colors);
        cl.setAlpha(255);
        fill(cl);
        stroke(0);
        strokeWeight(3);
        beginShape();
        for(let a = 0; a < 2*PI; a+=2*PI/n){
            vertex(r*cos(a),r*sin(a));
        }
        endShape(CLOSE);
        i += 1;
    }   
    pop();
    drawingContext.restore();
}
```
---

OUTPUT 

 <img src = "/assets/images/0012a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0012b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0012c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0012d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0012e.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0012f.png" alt="Grid 1" width="500" height="500"> 

<img src = "/assets/images/0012g.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0012h.png" alt="Grid 1" width="500" height="500"> 

