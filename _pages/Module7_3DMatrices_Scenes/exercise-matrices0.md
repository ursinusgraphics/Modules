---
layout: exercise_matrix
permalink: "Module7/Exercise0"
title: "CS 476: Computer Graphics - Module 7 Exercise 0"
excerpt: "CS 476: Computer Graphics - Module 7 Exercise 0"
canvasasmtid: "216129"
canvaspoints: "1"

info:
  prev: "./Video0"
  next: "./Video1"
  points: 1
  instructions: "<p>Construct a matrix that turns the unit square into a 2x2 square (a scale by a factor of 2 in all dimensions), and which then translates it by the vector (-1, -1).  If you've gotten it right, it will keep the upper right corner fixed.  Please use the widget below to input your matrix and experiment, and when you believe you have the answer, enter your netid and the check/submit button below</p><div id = \"matrixdisplay\"></div>"
  goals:
    - Work with fundamental examples of matrix multiplications
    - Use homogenous coordinates to express a translation in matrix form
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  setupprocess: |
    let matrixDisplay = document.getElementById("matrixdisplay");
    let width = 400;
    let height = 400;
    let sideLength = 100;
    let res = addNCompositionMatrixWidgets(matrixDisplay, 1, true, false, width, height, sideLength);
    let AInputs = res.MInputs[0];
  feedbackprocess: | 
    let mat = textToMatrix(AInputs, true, false); 
    let correct = glMatrix.mat3.fromValues(2, 0, 0, 0, 2, 0, -1, -1, 1);
    outputToSend = JSON.stringify(mat);
  correctcheck: |
    glMatrix.mat3.equals(correct, mat) 

---
