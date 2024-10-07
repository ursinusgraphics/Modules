---
layout: exercise_javascript
permalink: "ModuleX_RayCasting/Exercise"
title: "CS 476: Computer Graphics - Module 11 Exercise"
excerpt: "CS 476: Computer Graphics - Module 11 Exercise"
canvasasmtid: "101749"
canvaspoints: "1"

info:
  prev: "./Video3"
  next: "./AABBNotes"
  points: 1
  instructions: "Fill in the method <code>getSphereNormal</code> to compute the normal at a point of intersection on the sphere.  Note that we're going back into Javascript/glmatrix library mode for a moment, but that this stuff is much simpler with the built-in functions in GLSL."
  goals:
    - Work with vector math to accomplish tasks for ray tracing

processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString.trim();
  correctcheck: |
    pos.includes("vec3(-0.5773502588272095, -0.5773502588272095, -0.5773502588272095).vec3(0.8451542258262634, 0.5070925354957581, 0.16903084516525269).vec3(0.986393928527832, 0, -0.16439898312091827)")
  incorrectchecks:
    - incorrectcheck: |
        pos.includes("vec3(-1, -1, -1).vec3(5, 3, 1).vec3(6, 0, -1)")
      feedback: "Try again: don't forget to normalize your normals!  Use the <code>normalize</code> or <code>length</code> functions in glMatrix"   
    - incorrectcheck: |
        pos.includes("vec3(0.5773502588272095, 0.5773502588272095, 0.5773502588272095).vec3(-0.8451542258262634, -0.5070925354957581, -0.16903084516525269).vec3(-0.986393928527832, 0, 0.16439898312091827)")
      feedback: "Try again: It looks like your vectors are pointed the wrong way"   

    - incorrectcheck: |
        pos.includes("vec3(1, 1, 1).vec3(-5, -3, -1).vec3(-6, 0, 1)")
      feedback: "Try again: It looks like your vectors are pointed the wrong way, and you also need to normalize them"
      


files:
  - filename: "Student Code"
    name: arrayutils
    ismain: false
    isreadonly: false
    isvisible: true
    code: |
        /**
         * Compute the normal of a sphere at a point on the sphere
         * 
         * @param {vec3} c: The center of the sphere
         * @param {vec3} p: The point of intersection
         **/
        function getSphereNormal(c, p) {
          let res = glMatrix.vec3.create();
          // TODO: Fill this in
          return res;
        }

  - filename: "Test Code Block"
    name: tester
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        let c1 = glMatrix.vec3.fromValues(1, 1, 1);
        let p1 = glMatrix.vec3.fromValues(0, 0, 0);
        let n1 = getSphereNormal(c1, p1);
        let s1 = glMatrix.vec3.str(n1);

        let c2 = glMatrix.vec3.fromValues(1, 2, 3);
        let p2 = glMatrix.vec3.fromValues(6, 5, 4);
        let n2 = getSphereNormal(c2, p2);
        let s2 = glMatrix.vec3.str(n2);

        let c3 = glMatrix.vec3.fromValues(-1, 0, 1);
        let p3 = glMatrix.vec3.fromValues(5, 0, 0);
        let n3 = getSphereNormal(c3, p3);
        let s3 = glMatrix.vec3.str(n3);
        console.log(s1 + "." + s2 + "." + s3);
---
