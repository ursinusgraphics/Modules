---
layout: exercise_matrix
permalink: "Module7/Exercise2"
title: "CS 476: Computer Graphics - Module 7 Exercise 2"
excerpt: "CS 476: Computer Graphics - Module 7 Exercise 2"
canvasasmtid: "100576"
canvaspoints: "1"

info:
  prev: "./Video2"
  next: "./Video3"
  points: 1
  instructions: "<p>Recall that rotation matrices in 2D commute.  But this turns out not to be the case for 3D rotations when the rotation axes are different.  Find two rotation matrices around different axes which lead to different results when applied in a different order</p><div id = \"matrixdisplay\"></div>"
  goals:
    - Construct 3D rotation matries
    - Explore the commutativity of 3D rotations
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  setupprocess: |
    let matrixDisplay = document.getElementById("matrixdisplay");
    let width = 200;
    let height = 200;
    let sideLength = 40;
    let res = addCommutativeMatrixGrid(matrixDisplay, false, true, width, height, sideLength, glMatrix.mat4.create(), glMatrix.mat4.create(), shaderPath, meshesPath);
    let AInputs = res.AInputs;
    let BInputs = res.BInputs;
  feedbackprocess: | 
    let A = textToMatrix(AInputs, false, true);
    let B = textToMatrix(BInputs, false, true);
    let AB = glMatrix.mat4.create();
    glMatrix.mat4.multiply(AB, A, B);
    let BA = glMatrix.mat4.create();
    glMatrix.mat4.multiply(BA, B, A);
    solution = JSON.stringify({"A":A, "B":B});
    function isOrthonormal4x4(M) {
      let orthogonal = true;
      for (let i = 0; i < 4; i++) {
        for (let j = i+1; j < 4; j++) {
          let sum = 0.0;
          for (let k = 0; k < 4; k++) {
            sum += M[i*4+k]*M[j*4+k];
          }
          if (Math.abs(sum) > 1e-5) {
            orthogonal = false;
          }
        }
      }
      let normal = true;
      for (let i = 0; i < 4; i++) {
        let sum = 0.0;
        for (let j = 0; j < 4; j++) {
          sum += M[i*4+j]*M[i*4+j];
        }
        if (Math.abs(sum-1) > 1e-3) {
          normal = false;
        }
      }
      return orthogonal && normal;
    }
  correctcheck: |
    isOrthonormal4x4(A) && isOrthonormal4x4(B) && !glMatrix.mat4.equals(AB, BA)
  incorrectchecks:
    - incorrectcheck: |
        !isOrthonormal4x4(A)
      feedback: "Try again: It looks like A is not a proper rotation matrix!</p>"    
    - incorrectcheck: |
        !isOrthonormal4x4(B)
      feedback: "Try again: It looks like B is not a proper rotation matrix!"   
    - incorrectcheck: |
        glMatrix.mat4.equals(AB, BA)
      feedback: "Try again: It looks like AB = BA"  
---
