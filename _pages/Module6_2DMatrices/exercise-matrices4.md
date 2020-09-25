---
layout: exercise_matrix
permalink: "Module6/Exercise4"
title: "CS 476: Computer Graphics - Module 6 Exercise 4"
excerpt: "CS 476: Computer Graphics - Module 6 Exercise 4"
canvasasmtid: "100178"
canvaspoints: "1"

info:
  prev: "./Video4"
  next: "./Video5"
  points: 1
  instructions: "<p>The matrix A below rotates a vector counter-clockwise by 30 degrees.  Construct a matrix B which is its inverse. Please use the widget below to input your matrix and experiment, and when you believe you have the answer, enter your netid and the check/submit button below</p><div id = \"matrixdisplay\"></div>"
  goals:
    - Construct the inverse of a matrix
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  setupprocess: |
    let matrixDisplay = document.getElementById("matrixdisplay");
    let width = 180;
    let height = 180;
    let sideLength = 40;
    let c = Math.cos(Math.PI/6);
    let s = Math.sin(Math.PI/6);
    let AInit = glMatrix.mat3.fromValues(c, -s, 0, s, c, 0, 0, 0, 1);
    let res = addNCompositionMatrixWidgets(matrixDisplay, 2, false, width, height, sideLength, [AInit]);
    let AInputs = res.MInputs[0];
    let BInputs = res.MInputs[1];
  feedbackprocess: | 
    let A = textToMatrix(AInputs);
    let B = textToMatrix(BInputs);
    let AB = glMatrix.mat3.create();
    glMatrix.mat3.multiply(AB, A, B);
    let eye = glMatrix.mat3.create();
    solution = JSON.stringify(B);
  correctcheck: |
    glMatrix.mat3.equals(AB, eye)

---
