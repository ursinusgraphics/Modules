---
layout: exercise_javascript_heightmap
permalink: "Module15/Exercise2"
title: "CS 476: Computer Graphics - Module 15 Exercise 2"
excerpt: "CS 476: Computer Graphics - Module 15 Exercise 2"
canvasasmtid: "104212"
canvaspoints: "1.5"

info:
  prev: "./Video2"
  points: 1.5
  instructions: "Change the function and adjust the isolevel so that the levelset consists of a loop inside of another loop.  In 3D as a heightmap, a surface where such an isolevel exists is a volcano."
  goals:
    - Manipulate heightmaps for levelset curve editing
    - Work with implicit representations of curves

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    let numComponents = getConnectedComponents(canvas.ms.contour.edges, canvas.ms.contour.vertices.length/2).components.length;

  correctcheck: numComponents == 2

function:
  code: |
        function fn(x, y) {
            function gauss(x, y, cx, cy, sigma) {
                const dx = x - cx;
                const dy = y - cy;
                return Math.exp(-(dx*dx+dy*dy)/(sigma*sigma));
            }
            return gauss(x, y, 0, 0, 0.2);
        }
---