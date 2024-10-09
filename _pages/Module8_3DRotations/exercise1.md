---
layout: exercise
language: javascript
permalink: "Module8/Exercise1"
title: "CS 476: Computer Graphics - Module 8 Exercise 2"
excerpt: "CS 476: Computer Graphics - Module 8 Exercise 2"
canvasasmtid: "217225"
canvaspoints: "1.5"

info:
  prev: "./Video1"
  next: "./Video2"
  points: 1.5
  instructions: "Finish the method <code>axisAngle2Rot3D</code> that constructs a 3x3 rotation matrix in column major order from a specified axis and angle.  Feel free to use any of the methods in the mat3 class in glMatrix"
  goals:
    - Convert an axis-angle representation to a 3x3 matrix

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("0.835,0.183,0.519,-0.5,0.647,0.575,-0.23,-0.74,0.632,0.826,0.504,0.251,-0.164,0.641,-0.75,-0.539,0.578,0.613")
  incorrectchecks:
    - incorrectcheck: |
      pos.includes("1,0,0,0,1,0,0,0,1,1,0,0,0,1,0,0,0,1")
      feedback: "Try again: It looks like you're returning what was in the starter code."    

files:
  - filename: "student.js"
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        var mat3 = glMatrix.mat3;

        /**
         * Construct a 3x3 rotation matrix in column major order 
         * from a specified axis and angle
         * 
         * @param {vec3}  a: The axis around which to rotate
         * @param {float} theta: The angle by which to rotate
         **/
        function axisAngle2Rot3D(a, theta) {
          let R = mat3.create(); // Start off as the identity matrix
          
          let A = [0, 0, 0, 0, 0, 0, 0, 0, 0]; // TODO: Change this

          R = mat3.multiplyScalarAndAdd(R, R, A, Math.sin(theta));
          // TODO: Finish this  

          return R;
        }

  - filename: "main.js"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let a = [-0.79, 0.45, -0.41];
        let theta = 5.3;
        let R = axisAngle2Rot3D(a, theta);
        let s = "";
        for (let i = 0; i < 9; i++) {
          s += Math.round(R[i]*1000)/1000 + ",";
        }
        a = [-0.789, -0.469,  0.397 ];
        theta = 1;
        R = axisAngle2Rot3D(a, theta);
        for (let i = 0; i < 9; i++) {
          s += Math.round(R[i]*1000)/1000 + ",";
        }
        console.log(s);


openFilesOnLoad: ["main.js", "student.js"]
---
