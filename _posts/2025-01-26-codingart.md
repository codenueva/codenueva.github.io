---
layout: post
title: Art Made With Code 3
date: 2025-01-26 09:45
category: artwithcode
author: codenueva
tags: [p5js,art,code,circles]
summary: 
---

Nothing fancy for today's sketch. Concentric circles in a square grid.

```
// 25 Jan 2025
// codenueva

let rows;
let cols; 
let margin; // outer margin for the entire sketch
let colors; //palette
let gap; // gap between nested rectangles

function setup() {
    createCanvas(600, 600);
    rows = int(random(5,20));
    //cols = int(random(5,20));
    cols = rows;
    margin = int(random(20,60));
    gap = int(random(4,8));
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
       

        // get the side with lesser length
        let dim = (rectWidth > rectHeight) ? rectHeight : rectWidth;
        // determine count of rectangles for nesting
      
        let dg = 2*gap;
        let n = (dim-dg)/dg;
         // draw the rectangles with or without black borders 
        noStroke();
        stroke(0,200);
        strokeWeight(2);
        let cl = random(colors);
        cl.setAlpha(250);
        fill(cl);
        rect(0,0,rectWidth, rectHeight);
        // draw the rectangles
        for(let k = 0; k < n+1; k+=1){
            let cl = random(colors);
            cl.setAlpha(250);  
            fill(cl);
            ellipse(0, 0, rectWidth-k*dg-10, rectHeight-k*dg-10);
        }
        pop();
        }
    }
}

```
OUTPUT 

 <img src = "/assets/images/0003a.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0003b.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0003c.png" alt="Grid 1" width="500" height="500"> 

 <img src = "/assets/images/0003d.png" alt="Grid 1" width="500" height="500"> 
 
 <img src = "/assets/images/0003e.png" alt="Grid 1" width="500" height="500"> 