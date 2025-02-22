---
layout: post
title: Art Made With Code 14
date: 2025-02-22 08:01
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
        divRow(x,y,rectWidth,rectHeight);
        drawingContext.restore();
        pop();
    }
    
}


function divRow(x,y,w,h){
    let vm = 10;
    let nc = random(8,20);
    let sp = random(4,15);
    let tw =((w/nc)-2*sp);
    push();
    translate(x,y);
    for(let i = 0; i < nc; i += 1){
        strokeWeight(4);
        stroke(0);
        noFill();
        let cl = random(colors);
        fill(cl);
        beginShape();
        vertex((2*i)*sp + i*tw, vm);
        vertex((2*i)*sp + (i+1)*tw, vm);
        vertex((2*i)*sp + i*tw + 0.5*tw, h-vm);
        endShape(CLOSE);
        cl = random(colors);
        fill(cl);
        beginShape();
        vertex((2*i+1)*sp + (i+1)*tw, vm);
        vertex((2*i+1)*sp + i*tw + 0.5*tw, h-vm);
        vertex((2*i+1)*sp + i*tw + 1.5*tw, h-vm);
        endShape(CLOSE);
        
    }
    pop();

}
```

OUTPUT 

 <img src = "/assets/images/0014a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0014b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0014c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0014d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0014e.png" alt="Grid 1" width="500" height="500"> 
