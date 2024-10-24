---
layout: exercise
language: javascript
permalink: "Module11/Exercise1"
title: "Module 11: Triangle Fans"
excerpt: "Module 11: Triangle Fans"
canvasasmtid: "217746"
canvaspoints: "2"
canvashalftries: 5

info:
  prev: "./Video1"
  next: "./Video2"
  points: 2
  instructions: ""
  goals:
    - To manipulate basic mesh data structures
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("[[0,1,2],[0,2,3],[0,3,4]],[[0,1,2],[0,2,3],[0,3,4],[0,4,5]]")
  incorrectchecks:
    - incorrectcheck: |
        pos.includes("eeeeeeeee")
      feedback: "Try again: It looks like you're returning the default value of 0 for every answer."    
 
files:
  - filename: "student.js"
    name: arrayutils
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
         * @param {int} N How many vertices are involved in the triangle fan
         * @return {2D Array} List of [[i1, j1, k1], [i2, j2, k2], ...] indices
         *                    for the triangles in a triangle fan with N vertices
         **/
        function constructTriangleList(N) {
          let tris = [];
          // TODO: Fill this in
          return tris;
        }

  - filename: "sortlist.js"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        function sortList(res) {
          for (let i = 0; i < res.length; i++) {
            res[i].sort();
          }
          return res;
        }

  - filename: "main.js"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let res1 = sortList(constructTriangleList(5));
        let res2 = sortList(constructTriangleList(6));
        console.log(JSON.stringify(res1) + "," + JSON.stringify(res2));

openFilesOnLoad: ["main.js", "student.js"]
---
