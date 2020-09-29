---
layout: exercise_javascript
permalink: "Module7/Exercise3"
title: "CS 476: Computer Graphics - Module 7 Exercise 3"
excerpt: "CS 476: Computer Graphics - Module 7 Exercise 3"
canvasasmtid: "100577"
canvaspoints: "1"

info:
  prev: "./Video3"
  next: "./Video4"
  points: 1
  instructions: "<p>The test code block has setup an object with a field \"grades\" in it, which is itself an object.  Fill in the function gradeChrisIDS301 to create an entry called \"ids301\" in the grades field whose value is \"grade\" </p></div>"
  goals:
    - Work with Javascript Object Notation (JSON)

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("100")

files:
  - filename: "Student Code"
    name: arrayutils
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
         * Compute the vector between two other vectors
         * 
         * @param {object} An object with a field "grades", which 
         *                 itself points to an object
         **/
        function gradeChrisIDS301(chris, grade) {
          // TODO: Fill this in.  Add an entry for IDS 301
          // in grades, and give him a grade of "grade"
        }

  - filename: "Test Code Block"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let chris = {"name":"Chris", "grades":{"cs476":100, "cs174":100} };
        gradeChrisIDS301(chris, 100);
        console.log(chris.grades.ids301);
---
