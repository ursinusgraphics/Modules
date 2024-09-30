---
layout: exercise
language: javascript
permalink: "Module8/Exercise0"
title: "CS 476: Computer Graphics - Module 8 Exercise 0"
excerpt: "CS 476: Computer Graphics - Module 8 Exercise 0"
canvasasmtid: "216849"
canvaspoints: "2"

info:
  prev: "./Video0"
  next: "./Video1"
  points: 2
  instructions: "Fill in the method <code>getAngles(R)</code> to extract <code>&alpha;</code>, <code>&beta;</code>, <code>&gamma;</code>, assuming that <b>R</b> is expressed as the product <h2><code>R<sub>Y</sub>(&alpha;) R<sub>X</sub>(&beta;) R<sub>Z</sub>(&gamma;)</code></h2>.  Note that you're given the matrix as a <code>mat4</code> which is <b>column major</b>.  The methods <code>Math.asin</code> and <code>Math.atan2</code> will come in handy.  No need to convert to degrees or to make the values positive.<p></p>"
  goals:
    - Convert between 3D rotation representations
    - Convert from a rotation matrix to Tait-Bryan angles (roll/pitch/yaw)

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("16.71,4.92,-120.17:-40.22,-14.12,129.85") || pos.includes("-0.29,0.09,-2.1:-0.7,-0.25,2.27")

files:
  - filename: "student.js"
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
         * Compute the complex product of two complex numbers 
         * represented as vectors
         * 
         * @param {mat4} x: A glMatrix mat4, in *column major order*
         **/
        function getAngles(R) {
          let alpha = 0, beta=0, gamma=0; // These are dummy values
          // TODO: Fill this in.  
          return {"alpha":alpha, "beta":beta, "gamma":gamma};
        }

  - filename: "main.js"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let res = getAngles([-0.45996176,-0.86138526,-0.21552406,0,0.84045837,-0.50065539,0.20730151,0,-0.28646975,-0.08578823,0.95424078,0,0,0,0,1]);
        let alpha = (Math.round(res.alpha*100)/100).toString();
        let beta = (Math.round(res.beta*100)/100).toString();
        let gamma = (Math.round(res.gamma*100)/100).toString();
        let s = alpha + "," + beta + "," + gamma;
        
        res = getAngles([-0.3682976087714904, 0.7444998480567603, -0.5568454432036434, 0.0, -0.6871370291961838, -0.6214335942495282, -0.3763814435457133, 0.0, -0.6262583927426798, 0.24400873792053612, 0.7404459206031069, 0.0, 0.0, 0.0, 0.0, 1.0]);
        alpha = (Math.round(res.alpha*100)/100).toString();
        beta = (Math.round(res.beta*100)/100).toString();
        gamma = (Math.round(res.gamma*100)/100).toString();
        s = s + ":" + alpha + "," + beta + "," + gamma;
        console.log(s);


openFilesOnLoad: ["main.js", "student.js"]
---
