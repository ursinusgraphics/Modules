---
layout: exercise_javascript
permalink: "Module9/Exercise2"
title: "CS 476: Computer Graphics - Module 9 Exercise 2"
excerpt: "CS 476: Computer Graphics - Module 9 Exercise 2"
canvasasmtid: "101244"
canvaspoints: "1"

info:
  prev: "./Video2"
  next: "./Video3"
  points: 1
  instructions: "<p>The test code block has setup an object with a field \"grades\" in it, which is itself an object.  Fill in the function gradeChrisIDS301 to create an entry called \"ids301\" in the grades field whose value is \"grade\" </p></div>"
  goals:
    - Work with Javascript Object Notation (JSON)

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("0+2i.5+-1i")

files:
  - filename: "Student Code"
    name: arrayutils
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
         * Compute the vector between two other vectors
         * 
         * @param {vec2} x: The first complex number
         * @param {vec2} y: The second complex number
         **/
        function complexMultiply(x, y) {
          let res = glMatrix.vec2.create();
          // TODO: Fill this in.  

          return res;
        }

  - filename: "Test Code Block"
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
---
