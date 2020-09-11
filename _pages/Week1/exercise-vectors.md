---
layout: exercise_javascript
permalink: "Week1/Vectors8"
title: "CS 476: Computer Graphics - Vectors Part 1 Coding Exercise"
excerpt: "CS 476: Computer Graphics - Vectors Part 1 Coding Exercise"
canvasasmtid: "99102"
canvaspoints: "2"
canvashalftries: 5

info:
  prev: "./Vectors7"
  points: 2
  instructions: "Fill in the function <code>vectorBetween</code>, which takes in two <code>glMatrix.vec3</code> objects and which turns a <code>glMatrix.vec3</code> object representing the vector from the first vector to the second vector.  Please refer to <a href = \"http://glmatrix.net/docs/module-vec3.html\">the documentation</a> to see which functions might be useful."
  goals:
    - To use the glMatrix library and reference its API
    - To implement vector operations in code
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("1,2,3.-1,-2,-3.1,-3,1.-1,3,-1")
  incorrectchecks:
    - incorrectcheck: |
        pos.includes("0,0,0.0,0,0.0,0,0.0,0,0")
      feedback: "Try again: It looks like you're returning the default value of 0 for every coordinate in the new vector."    
    - incorrectcheck: |
        pos.includes("a is undefined")
      feedback: "Try again: It looks like you're forgetting to include the result variable as a parameter in a vec3 method."    
    - incorrectcheck: |
        pos.includes("-1,-2,-3.1,2,3.-1,3,-1.1,-3,1")
      feedback: "Try again: It looks like you're doing v1-v2, but recall that the vector from v1 to v2 is actually v2-v1!."   
 
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
         * @param {glMatrix.vec3} v1 The first vector
         * @param {glMatrix.vec3} v2 The second vector
         * @return {glMatrix.vec3} A vector that points in the direction from
         *                         v1 to v2 and which has the length of the distance
         *                         between v1 and v2
         **/
        function vectorBetween(v1, v2) {
          let result = glMatrix.vec3.create();
          // TODO: Fill this in
          return result;
        }

  - filename: "Test Code Block"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let v1 = glMatrix.vec3.fromValues(0, 0, 0);
        let v2 = glMatrix.vec3.fromValues(1, 2, 3);
        let v3 = glMatrix.vec3.fromValues(0, 5, 2);
        let res1 = vectorBetween(v1, v2);
        let res2 = vectorBetween(v2, v1);
        let res3 = vectorBetween(v3, v2);
        let res4 = vectorBetween(v2, v3);
        console.log(res1 + "." + res2 + "." + res3 + "." + res4);
---
