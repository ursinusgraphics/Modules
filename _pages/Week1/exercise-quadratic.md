---
layout: exercise
language: javascript
permalink: "Week1/Quadratic"
title: "Javascript Example Module: Quadratic Formula"
excerpt: "Javascript Example Module: Quadratic Formula"
canvasasmtid: "207823"
canvaspoints: "2"
canvashalftries: 5

info:
  prev: "./Javascript1"
  next: "./Javascript2"
  points: 2
  instructions: "Write a function that computes the first root of the <a href=\"https://en.wikipedia.org/wiki/Quadratic_equation\">quadratic equation</a> (NOTE: We will actually find a practical use of this very soon).  In addition to multiplying b by itself, you can compute <code>b*b</code> using the <code><a href = \"https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/pow\">Math.pow</a></code> function.  The <code><a href = \"https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt\">Math.sqrt()</a></code> function takes a single parameter, which is the number whose root should be computed, and returns the result.  Now complete the code below"
  goals:
    - To write mathematical expressions in Javascript
    - To write a function that computes an expression and returns its result
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("3,1") || pos.includes("3.0,1.0")        
 
files:
  - filename: "student.js"
    name: driver
    ismain: false
    isreadonly: false
    isvisible: true
    code: | 
         function getQuadraticRoots(a, b, c) {
            // TODO: Fill this in
            return 0; // This is a dummy value
         }

  - filename: "main.js"
    ismain: true
    name: main
    isreadonly: true
    isvisible: true
    code: |
        // Run some tests on the method
        let ans1 = getQuadraticRoots(1, -1, -6);
        let ans2 = getQuadraticRoots(1, 0, -1);
        console.log(ans1 + "," + ans2);
        
openFilesOnLoad: ["main.js", "student.js"]
---

## Quadratic Formula

For reference, the quadratic formula is:

<span>\\[\frac{-b \pm \sqrt{(b^{2} - 4ac)}}{2a}\\]</span>

given an equation:

<span>\\[ax^{2} + bx + c = 0\\]</span>

In this exercise, you can simply compute one of the roots, as follows:

<span>\\[\frac{-b + \sqrt{(b^{2} - 4ac)}}{2a}\\]</span>