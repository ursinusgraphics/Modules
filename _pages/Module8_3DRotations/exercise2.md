---
layout: exercise
language: javascript
permalink: "Module8/Exercise2"
title: "CS 476: Computer Graphics - Module 8 Exercise 2"
excerpt: "CS 476: Computer Graphics - Module 8 Exercise 2"
canvasasmtid: "216603"
canvaspoints: "1.5"

info:
  prev: "./Video2"
  points: 1.5
  instructions: "Fill in the method <code>complexMultiply</code> to perform a complex multiplication between two complex numbers, using <code>vec2</code> from the glMatrix library to store the complex numbers in an array of 2 elements.  Recall that the complex product between <b>a+bi</b> and <b>c+di</b> is <b>(ac-bd) + (ad+bc)i"
  goals:
    - Implement complex multiplication in code

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("0+2i.5+-1i")

files:
  - filename: "student.js"
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
         * Compute the complex product of two complex numbers 
         * represented as vectors
         * 
         * @param {vec2} x: The first complex number
         * @param {vec2} y: The second complex number
         **/
        function complexMultiply(x, y) {
          let res = glMatrix.vec2.create();
          // TODO: Fill this in.  

          return res;
        }

  - filename: "main.js"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let c1 = glMatrix.vec2.fromValues(1, 1); // 1 + i
        let c1xc1 = complexMultiply(c1, c1); // Result should be 2i
        let c2 = glMatrix.vec2.fromValues(2, -3); // 2 - 3i
        let c1xc2 = complexMultiply(c1, c2); // Result should be 5-i
        console.log(c1xc1[0] + "+" + c1xc1[1] + "i" + "." + c1xc2[0] + "+" + c1xc2[1] + "i");

openFilesOnLoad: ["main.js", "student.js"]
---
