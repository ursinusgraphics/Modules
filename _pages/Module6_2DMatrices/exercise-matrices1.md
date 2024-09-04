---
layout: exercise_matrix
permalink: "Module6/Exercise1"
title: "CS 476: Computer Graphics - Module 6 Exercise 1"
excerpt: "CS 476: Computer Graphics - Module 6 Exercise 1"
canvasasmtid: "215689"
canvaspoints: "1"

info:
  prev: "./Video1"
  next: "./Video2"
  points: 1
  instructions: "<p>We saw a matrix that stretches vectors by a factor of 2.  Find a matrix that <b>compresses</b> vectors by a factor of 2 <b>along the x-axis</b>; that is, it squashes them in (the opposite of stretching) along the x-axis. Please use the widget below to input your matrix and experiment, and when you believe you have the answer, enter your netid and the check/submit button below</p><div id = \"matrixdisplay\"></div>"
  goals:
    - Work with fundamental examples of matrix multiplications
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  setupprocess: |
    let matrixDisplay = document.getElementById("matrixdisplay");
    let width = 400;
    let height = 400;
    let sideLength = 100;
    let res = addNCompositionMatrixWidgets(matrixDisplay, 1, false, false, width, height, sideLength);
    let AInputs = res.MInputs[0];
  feedbackprocess: | 
    let mat = textToMatrix(AInputs); 
    let correct = glMatrix.mat3.fromValues(0.5, 0, 0, 0, 1, 0, 0, 0, 1);
    outputToSend = mat[0] + " " + mat[3] + "\n" + mat[1] + " " + mat[4];
  correctcheck: |
    glMatrix.mat3.equals(correct, mat) 

---
