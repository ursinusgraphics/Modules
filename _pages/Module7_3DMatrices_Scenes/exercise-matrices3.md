---
layout: exercise_matrix
permalink: "Module6/Exercise3"
title: "CS 476: Computer Graphics - Module 6 Exercise 3"
excerpt: "CS 476: Computer Graphics - Module 6 Exercise 3"
canvasasmtid: "100176"
canvaspoints: "1"

info:
  prev: "./Video3"
  next: "./Video4"
  points: 1
  instructions: "<p>Find two matrices that do not commute; that is, construct a matrix A and a matrix B so that B(Ax) is not the same as A(Bx).  Please use the widget below to input your matrices and experiment, and when you believe you have the answer, enter your netid and the check/submit button below</p><div id = \"matrixdisplay\"></div>"
  goals:
    - Discover a counter example for the commutativity of matrix multiplication
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  setupprocess: |
    let matrixDisplay = document.getElementById("matrixdisplay");
    let width = 180;
    let height = 180;
    let sideLength = 40;
    let res = addCommutativeMatrixGrid(matrixDisplay, false, false, width, height, sideLength);
    let AInputs = res.AInputs;
    let BInputs = res.BInputs;
  feedbackprocess: | 
    let A = textToMatrix(AInputs);
    let B = textToMatrix(BInputs);
    let AB = glMatrix.mat3.create();
    glMatrix.mat3.multiply(AB, A, B);
    let BA = glMatrix.mat3.create();
    glMatrix.mat3.multiply(BA, B, A);
    solution = JSON.stringify({"A":A, "B":B});
  correctcheck: |
    !glMatrix.mat3.equals(AB, BA)

---
