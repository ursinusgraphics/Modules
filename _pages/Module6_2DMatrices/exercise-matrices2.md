---
layout: exercise_matrix
permalink: "Module6/Exercise2"
title: "CS 476: Computer Graphics - Module 6 Exercise 2"
excerpt: "CS 476: Computer Graphics - Module 6 Exercise 2"
canvasasmtid: "100174"
canvaspoints: "1"

info:
  prev: "./Video2"
  next: "./Video3"
  points: 1
  instructions: "<p>Find a matrix that rotates vectors counter-clockwise by 270 degrees (or alternatively, rotates it 90 degrees clockwise). Please use the widget below to input your matrix and experiment, and when you believe you have the answer, enter your netid and the check/submit button below</p><div id = \"matrixdisplay\"></div>"
  goals:
    - Construct a 2D rotation matrix
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  setupprocess: |
    let matrixDisplay = document.getElementById("matrixdisplay");
    let width = 400;
    let height = 400;
    let sideLength = 100;
    let res = addNCompositionMatrixWidgets(matrixDisplay, 1, false, width, height, sideLength);
    let AInputs = res.MInputs[0];
  feedbackprocess: | 
    let mat = textToMatrix(AInputs); 
    solution = JSON.stringify(mat);
    let correct = glMatrix.mat3.fromValues(0, -1, 0, 1, 0, 0, 0, 0, 1);
  correctcheck: |
    glMatrix.mat3.equals(correct, mat)

---
