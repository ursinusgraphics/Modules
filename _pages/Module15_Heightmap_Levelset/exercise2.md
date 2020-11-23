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
    let vs = canvas.ms.getContourLoops();
    let poly1InPoly2 = true;
    let poly2InPoly1 = true;
    if (vs.length == 2) {
      // Check all points in polygon1 against polygon2
      for (let k = 0; k < vs[0].length && poly1InPoly2; k++) {
        poly1InPoly2 &= pointInsidePolygon2D(vs[0][k], vs[1]);
      }
      // Check all points in polygon2 against polygon1
      for (let k = 0; k < vs[1].length && poly2InPoly1; k++) {
        poly2InPoly1 &= pointInsidePolygon2D(vs[1][k], vs[0]);
      }
    }
    console.log("numComponents = " + vs.length);
    console.log("poly1InPoly2 = " + poly1InPoly2);
    console.log("poly2InPoly1 = " + poly2InPoly1);

  correctcheck: vs.length == 2 && (poly1InPoly2 || poly2InPoly1)

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