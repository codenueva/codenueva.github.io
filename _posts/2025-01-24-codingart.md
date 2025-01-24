---
layout: post
title: Art Made With Code 2
date: 2025-01-24 10:42
category: artwithcode
author: codenueva
tags: [p5js,art,code]
summary: 
---

Today's sketch is an extension of [sketch 1](https://codenueva.github.io/artwithcode/2025/01/22/codingart.html).
The code is modified to render the rectangles in a nested manner each with a random color. 


```
let rows;
let cols; 
let margin; // outer margin for the entire sketch
let colors; //palette
let gap; // gap between nested rectangles

function setup() {
    createCanvas(600, 600);
    rows = int(random(5,20));
    cols = int(random(5,20));
    margin = int(random(20,60));
    gap = int(random(4,7));
    colors = [color(255, 224, 61), color(254, 72, 48), color(211, 48, 51), 
              color(109, 53, 138), color(28, 80, 158), color(0, 149, 60)];
    
}


function draw() {
    
    noLoop();
    // choose a random color for background
    background(random(colors)); 
    let rectWidth = (width-2*margin)/cols;
    let rectHeight = (height-2*margin)/rows;
    // choose a random color for border
    stroke(random(colors));
    strokeWeight(20);
    noFill();
    // draw an outer border or comment this out to do it without border
    rect(margin,margin,width-2*margin,height-2*margin);
    
    for (let i = 0; i < cols; i++) {
        for (let j = 0; j < rows; j++) {
        // calculate position for each rectangle
        push();
        let x =  margin + i * rectWidth ;
        let y =  margin + j * rectHeight ;
        translate(x + rectWidth/2,y +  rectHeight/2); 
        // draw nested rectangles
        rectMode(CENTER); 
        // draw the rectangles with or without black borders 
        //noStroke();
        stroke(0,200);
        strokeWeight(2);
        // get the side with lesser length
        let dim = (rectWidth > rectHeight) ? rectHeight : rectWidth;
        // determine count of rectangles for nesting
        let dg = 2*gap;
        let n = (dim-dg)/dg;
        // draw the rectangles
        for(let k = 0; k < n; k+=1){
            let cl = random(colors);
            cl.setAlpha(250);
            fill(cl);
            rect(0, 0, rectWidth-k*dg, rectHeight-k*dg);
        }
        pop();
        }
    }
}
```
OUTPUT 

 <img src = "/assets/images/0002a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0002b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0002c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0002d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0002e.png" alt="Grid 1" width="500" height="500"> 