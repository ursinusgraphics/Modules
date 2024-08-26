---
layout: exercise
language: javascript
permalink: "Week1/ArrayMinIndex"
title: "Javascript Example Module: Array Min Index"
excerpt: "Javascript Example Module: Array Min Index"
canvasasmtid: "207822"
canvaspoints: "2"
canvashalftries: 5

info:
  prev: "./Javascript2"
  next: "./Javascript3"
  points: 2
  instructions: "Fill in the function <code>getMinIndex</code>, which takes in an array numerical values and which should return the index of the minimum element in the array.  You must handle the following two special cases: <ol><li>If there are ties, it should return the lowest index among the ties</li><li>If the array is empty, your program should return 0 without crashing</li></ul>"
  goals:
    - To do proper array indexing
    - To use loops in concert with arrays
    - To keep track of multiple auxiliary variables in a loop
    - To properly define methods
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("2.1.0")
  incorrectchecks:
    - incorrectcheck: |
        pos.includes("undefined")
      feedback: "Try again: It looks like you're going out of bounds of the array somewhere."    
    - incorrectcheck: |
        pos.includes("0.0.0")
      feedback: "Try again: It looks like you're returning the default value of 0 for every answer."    
 
files:
  - filename: "student.js"
    name: arrayutils
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
         * @param {list} arr The given array
         * @return {int} The index of the minimum element in the array 
         **/
        function getMinIndex(arr) {
          return 0;
        }

  - filename: "main.js"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let arr0 = [3, 5, 0, 8, 0, 2];
        let min0 = getMinIndex(arr0);
        let arr1 = [9, -3, 4, -3, 2, 5, 3, 2];
        let min1 = getMinIndex(arr1);
        let arr2 = [];
        let min2 = getMinIndex(arr2);
        console.log(min0 + "." + min1 + "." + min2);

openFilesOnLoad: ["main.js", "student.js"]
---
