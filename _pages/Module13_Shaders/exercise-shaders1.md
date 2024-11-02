---
layout: module
permalink: "Module13Shaders/Exercise1"
title: "CS 476: Computer Graphics - Module 13 Shaders Exercise 1"
excerpt: "CS 476: Computer Graphics - Module 13 Shaders Exercise 1"

info:
  prev: "./Video1"
  next: "./Video2"
---

<p>
If you haven't already, <a href = "https://github.com/ursinusgraphics/HW5_Shaders/archive/refs/heads/master.zip">click here</a> to download the starter code for assignment 3, which also includes code for this module, the next module, and in-class exercises this week.  For this exercise, modify the buffers in <code>triangle.js</code> so that when you run <code>triangle.html</code>, it draws an equilateral triangle with yellow in the lower left, cyan in the lower right, and magenta at the top, as shown below
</p>

<img src = "../images/Unit4/ShaderExercise1.png">

<p>
  Recall that cyan is rgb(0, 1, 1), magenta is rgb(1, 0, 1), and yellow is rgb(1, 1, 0).  Recall also that the height of an equilateral triangle whose base is length 1 along the x-axis is sqrt(3)/2.
</p>

<p>
When you are finished, <a href = "https://ursinus.instructure.com/courses/18079/assignments/218103">click here</a> to upload your modified <code>triangle.js</code> file to Canvas.
</p>

<h3>Automatic Barycentric</h3>
<p>
For your reference, recall that barycentric interpolation of colors is performed automatically in fragment shaders
</p>
<img src = "../images/Unit4/ShaderBarycentricColors.svg">