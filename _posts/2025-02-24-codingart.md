---
layout: post
title: Art Made With Code 15
date: 2025-02-24 09:57
category: artwithcode
author: codenueva
tags: [p5js,art,code,patterns]
summary: 
---

Patterns in rows. 

```
// 16 Feb 2025
// codenueva

let rows;
let cols; 
let margin; // outer margin for the entire sketch
let rmargin; // margin for each cell
let colors; //palette

function setup() {
    createCanvas(900, 900);
    rows = int(random(8,20));
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
        drawingContext.save();
        rect(x,y,rectWidth,rectHeight);
        drawingContext.clip();
        drawSineWave(x,y,rectWidth,rectHeight);
        drawingContext.restore();
        pop();
    }
    
}


function drawSineWave(x,y,w,h){
    push();
    translate(x,y);
    let cl = random(colors);
    fill(cl);
    strokeWeight(4);
    stroke(0);
    let frequency = 3;
    let sp = 8
    beginShape();
    for (let x = 0; x < w + 1; x++) {    
        let angle = map(x,0,w,0,2*PI);
        let y1 = sin(2*PI*angle*frequency);
        let y = map(y1,-1,1,sp,h-sp)
        vertex(x, y);
    }
    endShape();
    
    strokeWeight(2);
    cl = random(colors);
    fill(cl);
    for (let x = 0; x < w + 1; x++) {    
        let angle = map(x,0,w,0,2*PI);
        let y1 = sin(2*PI*angle*frequency);
        if(y1 > 0.99){
            ellipse(x,3*sp,6,6);
        }
        if(y1 < -0.99){
            ellipse(x,h-3*sp,6,6);
        }
        
    }
   
}
```

OUTPUT 

 <img src = "/assets/images/0015a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0015b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0015c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0015d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0015e.png" alt="Grid 1" width="500" height="500"> 