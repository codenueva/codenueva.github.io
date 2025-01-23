---
layout: post
title: Art Made With Code 1
date: 2025-01-22 18:55
category: artwithcode
author: codenueva
tags: [p5js,art,code]
summary: 
---

Restarting creative coding after a gap of more than a year. The plan is to start from the basics and sketch one work each day.
The hope is to overcome the barriers that I faced last couple of attempts - both in terms of creativity and 
complexity of coding (the math, the algorithms, etc)

Today's work - template for a simple grid of given number of columns and rows.The code is self explainatory.

```
let rows;
let cols; 
let margin; // outer margin for the entire sketch
let rmargin; // margin for each cell
let colors; //palette

function setup() {
    createCanvas(900, 900);
    rows = int(random(5,25));
    cols = int(random(5,25));
    margin = int(random(20,60));
    rmargin = int(random(2,10));
    colors = [color(255, 224, 61), color(254, 72, 48), color(211, 48, 51), 
              color(109, 53, 138), color(28, 80, 158), color(0, 149, 60)];
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
        // Draw rectangle with random color
        rectMode(CENTER); 
        let cl = random(colors);
        cl.setAlpha(250);
        fill(cl);
        stroke(0);
        strokeWeight(rmargin);
        rect(0, 0, rectWidth, rectHeight);
        pop();
        }
    }
}
```

OUTPUT 

 <img src = "/assets/images/0001a.png" alt="Grid 1" width="500" height="500"> 
 <img src = "/assets/images/0001b.png" alt="Grid 1" width="500" height="500"> 