---
layout: exercise
language: javascript
permalink: "Week1/JavascriptGlobalBug"
title: "CS 476: Computer Graphics - Vectors Part 1 Coding Exercise"
excerpt: "CS 476: Computer Graphics - Vectors Part 1 Coding Exercise"
canvasasmtid: "207824"
canvaspoints: "1.5"
canvashalftries: 5

info:
  prev: "./Javascript3"
  points: 1.5
  instructions: "Fix the method <code>sum2DArr</code> so that it no longer goes through an infinite loop"
  goals:
    - To use the glMatrix library and reference its API
    - To implement vector operations in code
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("120")
 
files:
  - filename: "student.js"
    name: arrayutils
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
        * Sum all of the elements in a particular row of a 2D array
        * @param {2d array} arr A 2d array of numbers
        * @param {int} row A row index of a 2d array
        */
        function sumRow(arr, row) {
            sum = 0;
            for (i = 0; i < arr[row].length; i++) {
                sum += arr[row][i];
            }
            return sum;
        }

        /**
        * Sum all of the elements in a 2d array
        * @param {2d array} arr A 2d array of numbers
        */
        function sum2DArray(arr) {
            sum = 0;
            for (i = 0; i < arr.length; i++) {
                sum += sumRow(arr, i);
            }
            return sum;
        }

  - filename: "main.js"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let arr = [ [1, 2, 3], 
                    [4, 5, 6], 
                    [7, 8, 9],
                    [10, 11, 12],
                    [13, 14, 15]];
        console.log(sum2DArray(arr));

openFilesOnLoad: ["main.js", "student.js"]
---
