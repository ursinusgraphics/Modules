---
layout: exercise_javascript
permalink: "Module16/Exercise1"
title: "CS 476: Computer Graphics - Module 16 Bounding Sphere Exercise"
excerpt: "CS 476: Computer Graphics - Module 16 Bounding Sphere Exercise"
canvasasmtid: "104644"
canvaspoints: "1.5"

info:
  prev: "./Video1"
  points: 1.5
  instructions: "Fill in the method <code>spheresIntersect(c1, r1, c2, r2)</code> to determine whether two spheres intersect; that is, compare the distance between their centers to the sum of their radii."
  goals:
    - Work with vector math to compute whether two spheres intersect

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("true.false.false.true")
      


files:
  - filename: "Student Code"
    name: arrayutils
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
         * Compute the complex product of two complex numbers 
         * represented as vectors
         * 
         * @param {vec3} c1: The center of the first sphere
         * @param {float} r1: Radius of the first sphere
         * @param {vec3} c2: The center of the second sphere
         * @param {float} r2: Radius of the second sphere
         **/
        function spheresIntersect(c1, r1, c2, r2) {
          let intersect = false;
          // TODO: Fill this in
          return intersect;
        }

  - filename: "Test Code Block"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let c1 = glMatrix.vec3.fromValues(1, 1, 1);
        let r1 = 1;
        let c2 = glMatrix.vec3.fromValues(0, 0, 0);
        let r2 = 0.8;
        let s1 = spheresIntersect(c1, r1, c2, r2);

        c1 = glMatrix.vec3.fromValues(1, 0, 0);
        r1 = 0.4;
        c2 = glMatrix.vec3.fromValues(2, 0, 0);
        r2 = 0.45;
        let s2 = spheresIntersect(c1, r1, c2, r2);

        c1 = glMatrix.vec3.fromValues(10, 0, 0);
        r1 = 4;
        c2 = glMatrix.vec3.fromValues(2, 0, 0);
        r2 = 2;
        let s3 = spheresIntersect(c1, r1, c2, r2);


        c1 = glMatrix.vec3.fromValues(10, 0, 0);
        r1 = 8;
        c2 = glMatrix.vec3.fromValues(0, 10, 0);
        r2 = 8;
        let s4 = spheresIntersect(c1, r1, c2, r2);

        console.log(s1 + "." + s2 + "." + s3 + "." + s4);
---
